---
title: NRES 898 Week 8
layout: page
root: .
venue: "University of Nebraska-Lincoln"      # brief name of host site without address (e.g., "Euphoric State University")
---
## Week 8: Even moRe

See [the bottom of this page](#assignment) for this weeks Challenge. By all means do the challenges in the readings; the answers are all at the bottom of each page. So, they are not the best option for assessment! 

### Writing a function

* [Video on defining a function](https://youtu.be/Gs8x-3G6K14)
* [Video on scope and return values](https://youtu.be/ArN19Ou0U-U)
* [Video on pass by value](https://youtu.be/Ouopr7OSWHQ)
* [Reading for the lesson](http://swcarpentry.github.io/r-novice-gapminder/07-functions.html)

### Writing data

* [Video on writing data to files](https://youtu.be/NY4-Top_zC0)
* [Reading for the lesson](http://swcarpentry.github.io/r-novice-gapminder/11-writing-data.html)

### Split - apply - combine 

* [Video about split - apply - combine](https://youtu.be/XPFf4_yf7YQ)
* [Reading for the lesson](http://swcarpentry.github.io/r-novice-gapminder/12-plyr.html)

### Split - apply - combine and other data manipulation the dplyr way

* [Video about dplyr select, filter & mutate](https://youtu.be/aKHNwgnmpO0)
* [Video about summarize & group_by](https://youtu.be/IbiHzLsKc50)
* [Reading for the lesson](http://swcarpentry.github.io/r-novice-gapminder/13-dplyr.html)

### EXTRA: using git pull to sync a local repository with a remote

We've done a great deal of cloning repositories, but not so much "pulling". [Here is a short \(~3 minutes\) video](https://youtu.be/ZBNpuxNITYo) of me using git pull inside RStudio to update a project.

### Manipulating data from long to wide and back again

The reading refers to a dataframe called `gap_wide`, which can be [downloaded here](assets/gap-wide.csv). Save it in your data subdirectory, and use `gap_wide <- read.csv("data/whatevernameyouused.csv")` to read it in to the workspace. 

* [Video about long to wide and back](https://youtu.be/NeSbrvUIYHc)
* [Reading for the lesson](http://swcarpentry.github.io/r-novice-gapminder/14-tidyr.html)

### Assignment

The file for this weeks assignment will be a commented R script. The file should be saved with a name like `yourlastname_week8.R`, and uploaded as an attachment. At the top of the file write a comment \(start the line with `#`\) with the week number and your name on one line. If none of that makes sense, go watch the start of [the video for subsetting vectors](https://youtu.be/LZB3x6hNZ9M). 

Download [this dataset of average temperatures by county in Nebraska](assets/NE_county_30yr_avg_temp.csv) into your data subdirectory. Make another subdirectory called `output`. Write code to do the following:

1. Read in the dataset, and convert it to a long format data frame. The result will have three columns: County, month, and avgTemp. Don't forget to load any packages you need using `library()` at the top of your script.
2. Use `ddply()` with an anonymous function, **OR** `dplyr` verbs to create a dataframe with the average annual temperature for each county. 
3. Write out that dataframe to a csv file called `yourlastname_week8_avgtemp.csv` in a subdirectory called `output`
4. Make a line plot of temperature by month with a seperate line for each county. Save it into a png file in the graphs subdirectory called `yourlastname_week8_tempplot.png`. \(hint: use aes(group=County) somewhere\)

I should be able to run your script from the main directory of the project created in week 6 using `source("code/yourlastname_week8.R")` from a clean start of R. To test your code to make sure it works without errors, first click on the Session menu, and choose `Restart R`. Then open your file and click the `source` button in the top right corner. This will load your file and run it; any output to the console is suppressed. Check the date and time of the saved image file to make sure the script ran correctly. 
 
This challenge is due on Friday of Week 8 \(Mar 4\) at 5 pm. Late assignments will receive 
a score of zero unless prior approval is granted.  
