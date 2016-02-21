---
title: NRES 898 Week 7
layout: page
root: .
venue: "University of Nebraska-Lincoln"      # brief name of host site without address (e.g., "Euphoric State University")
---
## Week 7: moRe

For this weeks Challenges I want something a little different. By all means do the challenges in the readings; the answers are all at the bottom of each page. So, they are not the best option for assessment! See the heading "Assignment" below for what I want you to turn in this week. 

### Subsetting Data Structures

* [Video for subsetting Vectors](https://youtu.be/LZB3x6hNZ9M)
* [Video for subsetting factors, matrices and lists](https://youtu.be/GXWCrQVW5Dk)
* [Reading for the Lesson](http://swcarpentry.github.io/r-novice-gapminder/06-data-subsetting.html) Ignore the last bit on dataframes.

### Data Frames

* [Video introducing dataframes](https://youtu.be/2DiPjT4zLjU)
* [Video for reading in data](https://youtu.be/jWpkzPLLKg8)
* [Reading for the Lesson](http://swcarpentry.github.io/r-novice-gapminder/05-data-structures-part2.html)

### Creating publication quality graphics

* [Video introduction to ggplot](https://youtu.be/8Gew6UYqF0s)
* [Video on transformations and statistics](https://youtu.be/jtaIvtvlGIQ)
* [Video on faceting and themes](https://youtu.be/DB0kVWnk724)
* [Reading for the lesson](http://swcarpentry.github.io/r-novice-gapminder/08-plot-ggplot2.html)
* There is an error in the video and reading -- the code for changing the legend name is incorrect. The correct code for making the plot is below.

```{r}
ggplot(gapminder,
       aes(x = year, y = lifeExp)) + 
  geom_line(aes(color = continent)) + 
  facet_wrap(~country) + 
  xlab("Year") + 
  ylab("Life Expectancy") + 
  scale_colour_discrete(name="Continent") +
  theme(axis.text.x = element_blank(), 
        axis.ticks.x = element_blank())
ggsave("graphs/lifebyyearbycountry.png")
```

### Vectorization

* [Video on vectorizing](https://youtu.be/xLTXFAttV7o)
* [Reading for the lesson](http://swcarpentry.github.io/r-novice-gapminder/09-vectorisation.html)
* The solutions for Challege 2 on that page use base graphics, not ggplot2. 



### Assignment

The file for this weeks assignment will be a commented R script. The file should be saved with a name like `yourlastname_week7.R`, and uploaded as an attachment. At the top of the file write a comment \(start the line with `#`\) with the week number and your name on one line. If none of that makes sense, go watch the start of [the video for subsetting vectors](https://youtu.be/LZB3x6hNZ9M). 

Write the code to do the following:

1. Read in the gapminder dataset.
2. Make a line plot of per capita GDP by year for each country in Asia. There should be a line for each country in Asia. There should not be any other continents in the plot.
3. Save the plot to a png file in the graphs subdirectory of your project. 

I should be able to run your script from the main directory of the project created in week 6 using `source("code/yourlastname_week7.R")` from a clean start of R. To test your code to make sure it works without errors, first click on the Session menu, and choose `Restart R`. Then open your file and click the `source` button in the top right corner. This will load your file and run it; any output to the console is suppressed. Check the date and time of the saved image file to make sure the script ran correctly. 
 
This challenge is due on Friday of Week 7 \(Feb 26\) at 5 pm. Late assignments will receive 
a score of zero unless prior approval is granted.  
