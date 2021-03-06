---
title: NRES 803 Lab 1
layout: page
root: .
---

The goal of this week's lab is just getting your feet wet, remembering how to use R, what a linear model is and getting some answers out. Like all labs, I expect you to submit an R Markdown file that I can compile to html. You should assume any data files are in a subdirectory called "data". Your file should *not* echo the code used. Answer the numbered questions in text, referring to graphical and tabular output as needed. You may use base graphics or ggplot2, according to your preference.

This dataset in package *faraway* contains the number of plant species on each of 30 islands in the Galapagos Archipelago, along with some attributes of each island. The species-area relationship suggests that the number of species should vary with area according to

\[
S = cA^z
\]

``` r
library(faraway)
data(gala)
library(ggplot2)
ggplot(gala, aes(x = Area, y = Species)) + 
  geom_point(size = 3)
```

The biggest trouble with this data is that there are a few very large islands and many small ones. If we take the logarithm of both sides of our model \[
log(S)=log(c)+zlog(A)
\] we have an equation that is a linear function of the logarithm of area.

``` r
gala.1 <- lm(log(Species)~log(Area),data=gala)
summary(gala.1)
# confidence intervals on the coefficients
confint(gala.1)
```

1.  What is the estimated value of *z*?
2.  What is the estimated value of *c*?
3.  Drakare et al. (2005) found the average value of *z* across many studies to be 0.27. Is the value of z from this dataset significantly different from 0.27?

Now examine the assumptions of this model. This uses base graphics, but too easy not to!

``` r
old.par = par(mfrow=c(2,2))
plot(gala.1)
par(old.par)
```

That is an textbook example of meeting all the assumptions! Starting from the upper left, the residuals are scattering evenly above and below the fitted line. The x - axis in that plot is the predicted values of species richness. The red line is a smooth fit that should be flat and close to 0. This tells us that the variance is constant, one of the assumptions of the linear model.

The Normal Q-Q plot plots the standardized residuals against the theoretical quantiles from a standard normal distribution. If the residuals are following a normal distribution then the points fall along the straight line in the plot. This is a direct test of the assumption that the residuals are normally distributed. Departures from a straight line here can often be corrected with appropriate transformations of your response variables.

The Scale-Location plot is similar to the Residuals vs. Fitted plot, but can make it easier to spot changes in variance. The smooth red line here should be close to 1, and flat. The final plot shows the residuals against the "leverage" of each point. Leverage is a measure of how much the fitted model would change when that point is eliminated. You should worry about points with large residuals (poorly fitted by model) and large leverage (having a large effect on the result). This plot shows contours of another statistic, the "Cook's distance", which is a combination of the size of the residual and the leverage. The rule of thumb is to worry about points with Cook's distance &gt; 2. All the points here have Cook's distance &lt; 0.5, so we are fine.

Notice that none of these plots test the assumption that the residuals are *independent* of each other. This is much trickier to test. In this case, it could be that islands closer together have more similar communities. Testing for spatial correlation is beyond the scope of the course, and we don't have the locations of the Islands anyway. But there is one variable that we could look at -- the distance to the largest island, Santa cruz.

``` r
# this gives us some nifty tools for extracting things from fitted models
library(broom)
test_distance <- augment(gala.1)
test_distance <- cbind(test_distance, Scruz = gala$Scruz)
ggplot(test_distance, aes(x = Scruz, y = .resid)) + 
  geom_point()
```

The two islands farthest away from Santa cruz have negative residuals. This means they have fewer species than expected for their size. It isn't clear that is enough of a violation of independence to worry about.

What do violations of assumptions look like? There is another dataset in package faraway that might have some. This is a plot of the proportion of people in a state born in the USA against the average income in that state.

``` r
ggplot(eco, aes(x=income, y = usborn)) +
  geom_point() + 
  geom_smooth(method = "lm")
```

The line is a linear model, and the grey polygon shows us the confidence limits on the mean. Let's fit that model explicitly and check the residuals using ggplot.

``` r
eco.1 <- lm(usborn ~ income, data = eco)
eco.test <- augment(eco.1, data = eco)
ggplot(eco.test, aes(x=.fitted, y = .resid)) +
  geom_point() +
  geom_smooth(color = "red")
```

So the confidence limits on the smooth line don't exclude zero anywhere, but it is far from flat either!

``` r
## different aesthetic
ggplot(eco.test, aes(sample = .std.resid)) +
  stat_qq() +
  geom_abline(color = "red")
```

So that is *clearly* not a straight line. The residuals are not following a normal distribution. The straight line here isn't quite the same as the straight line using `plot()`. That line goes through the first and third quartiles. But the general point would be the same. These points are not on a straight line.

``` r
## scale location plot
ggplot(eco.test, aes(x = .fitted, y = sqrt(abs(.std.resid)))) + 
  geom_point() + 
  geom_smooth() + 
  geom_hline(yintercept  = 1)
```

Here we can see that the variance is too small for fitted values &gt; 0.95 or so. I really like the confidence intervals on the smooths -- makes it much easier to interpret.

``` r
# leverage is the trace of the hat matrix
ggplot(eco.test, aes(.hat, .std.resid)) +
 geom_vline(size = 2, colour = "white", xintercept = 0) +
  geom_hline(size = 2, colour = "white", yintercept = 0) +
  geom_point(aes(size = .cooksd)) + geom_smooth(se = FALSE)
```

There are a couple points with largish positive residuals and substantial leverage. All the values for Cook's distance are small though, so not too alarming.

1.  Think about the possible values for the variable `usborn`. Do you expect this variable to follow a normal distribution? Why or why not?

Back to the Galapagos species data. Now we want to add some predictions from the model to our plot. This is a *critical* piece of analysis. I expect plots of raw data + predictions from models in *every* assignment in this course.

``` r
## always start by making a dataframe with the values of your covariates
nd = data.frame(Area=seq(min(gala$Area),max(gala$Area),10))
stats.gala <- glance(gala.1)
pred.1 <- augment(gala.1, newdata = nd)

# calculate the lower and upper 95% confidence limits on the mean
tcrit <- qt(0.975, df = stats.gala$df.residual)
pred.1$lwr <- with(pred.1, .fitted - tcrit * .se.fit)
pred.1$upr <- with(pred.1, .fitted + tcrit * .se.fit)

## put the raw data plot back first, then add
## lines and ribbons
ggplot(gala, aes(x = log(Area), y = log(Species))) + 
  geom_point(size = 3) + 
  geom_line(aes(x = log(Area), y = .fitted ), 
            data = pred.1, size = 2, color = "blue") + 
  geom_ribbon(aes(x = log(Area), ymin = lwr, ymax = upr, y = 0), 
              data = pred.1, alpha = 0.5)
```

1.  What is the smallest island where the *mean* \# of species is 55?

The confidence limits show us the range of uncertainty in the mean number of species for a given area. But the distribution of the actual observations is different. To understand the distribution of possible observations we need to calculate the *prediction limits*, where the variance is the sum of the variance in the fitted values and the residual variance.

``` r
pred.1$psigma <- sqrt(stats.gala$sigma^2 + pred.1$.se.fit^2)

pred.1$plwr <- with(pred.1, .fitted - tcrit * psigma)
pred.1$pupr <- with(pred.1, .fitted + tcrit * psigma)

ggplot(gala, aes(x = log(Area), y = log(Species))) + 
  geom_point(size = 3) + 
  geom_line(aes(x = log(Area), y = .fitted ), 
            data = pred.1, size = 2, color = "blue") + 
  geom_ribbon(aes(x = log(Area), ymin = lwr, ymax = upr, y = 0), data = pred.1, alpha = 0.25) +
  geom_ribbon(aes(x = log(Area), ymin = plwr, ymax = pupr, y = 0), data = pred.1, alpha = 0.25)
```

The lighter grey polygon shows the distribution of observations expected for each value of \(log(Area)\)

1.  What is the largest island where you have \(\ge 2.5\%\) chance of *observing* &lt; 55 species?

Finally, it is sometimes useful to make a plot on the untransformed scales. There should be an easy way to do this, but it isn't working just now.
