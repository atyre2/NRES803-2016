---
title: NRES 898 Week 9
layout: page
root: .
venue: "University of Nebraska-Lincoln"      # brief name of host site without address (e.g., "Euphoric State University")
---

## Week 9: wRapping up

Rather than chuck new stuff at you, I think this week I will arrange some additional practice with the 
skills you started building last week. That means more loading data, manipulating data, and making plots! 

See [the bottom of this page](#assignment) for this weeks Challenge. By all means do the challenges in the readings; the answers are all at the bottom of each page. So, they are not the best option for assessment! 

### Preparation

Start RStudio and create a new project called week9 in a location of your choice. I used the default working directory on my computer which is C:/users/atyre2/Documents; R abbreviates this with `~`. You want a new empty directory. You can create a git repository or not, as you choose. I am going to do that so I can share the repository with you. 

We'll use some datasets from the book Zuur et al. (2009) A Beginners Guide to R. This book is available electronically from the UNL library. It is getting a bit dated but a very good alternative reference for basic R work. Go to [their book website](http://www.highstat.com/book3.htm), scroll down to the heading *Data and R code*, right click on the link for all data in ascii format. Save that zip file to your data subdirectory of the week9 project directory we just created.

Now you need to extract the contents of that file into your data directory. Doing this varies by operating system, but it turns out that R has a function to do it for us! Assuming you still have RStudio open in the week9 project, you have downloaded the file `RBook.zip` into a subdirectory called data, you can do 

```r
unzip("data/RBook.zip", junkpaths = TRUE, exdir = "data")
```

The first argument is the path to the zip archive. The argument `junkpaths` tells `unzip()` to ignore any folder structure in the zip archive. The argument `exdir` tells `unzip()` to put the *ex*tracted files into the data subdirectory of the working directory. 

I deleted the zip archive after that -- it is now redundant. 

### Reading & cleaning data practice

We are going to try loading the file `data/BirdFluCases.txt` and figure out

*  What is the total number of bird flu cases per country?
*  What is the total number of cases per year?
*  Make a plot of cases per year by country. 
*  [Here's the video](https://youtu.be/j9nfmaTFYFU) of me doing it.

### Adding another dataset to a plot

What do you do if you want to add a dataset with a different dimension to a ggplot? A different number of rows? 
[Watch Drew struggle to figure it out!](https://youtu.be/lWcFeX_INYQ).

### More plotting examples from the R book

*  Just [a ramble through the basics of a scatterplot](https://youtu.be/DrORqU-Eotc), trying to reproduce a certain look.
*  [Messing around with more features of a scatterplot](https://youtu.be/uLcPZIO4ckM).
*  [Bar geoms and stats](https://youtu.be/sw5gG0GI6wU).

### Assignment

The file for this weeks assignment will be a commented R script. The file should be saved with a name like `yourlastname_week9.R`, and uploaded as an attachment. At the top of the file write a comment \(start the line with `#`\) with the week number and your name on one line. If none of that makes sense, go watch the start of [the video for subsetting vectors](https://youtu.be/LZB3x6hNZ9M). 

Make another subdirectory called `graphs`. Write code to do the following:

1.  Read in the dataset `TeethNitrogen.txt`. The result will have three columns: X15N, Age, and Tooth. Don't forget to load any packages you need using `library()` at the top of your script.
2.  Make a scatter plot of X15N vs. Age with a different color for each tooth. Add a smoothing curve to it for each tooth. Save it into a png file in the graphs subdirectory called `yourlastname_week9_toothplot_1.png`. 
3.  Repeat 2, but instead of coloring each tooth differently, use `facet_wrap(~Tooth)`. Save it into a png file in the graphs subdirectory called `yourlastname_week9_toothplot_2.png`.

I should be able to run your script from the main directory of the project created in week 6 using `source("code/yourlastname_week9.R")` from a clean start of R. To test your code to make sure it works without errors, first click on the Session menu, and choose `Restart R`. Then open your file and click the `source` button in the top right corner. This will load your file and run it; any output to the console is suppressed. Check the date and time of the saved image file to make sure the script ran correctly. 
 
This challenge is due on Friday of Week 9 \(Mar 11\) at 5 pm. Late assignments will receive 
a score of zero unless prior approval is granted.  
