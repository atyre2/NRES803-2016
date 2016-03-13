---
title: NRES 898 Week 10
layout: page
root: .
venue: "University of Nebraska-Lincoln"      # brief name of host site without address (e.g., "Euphoric State University")
---

## Week 10: Still more R

See [the bottom of this page](#assignment) for this weeks Challenge. 

### Preparation

We will use the same project directory as week 9. If you need to reconstruct that project directory and the data in it, [here are the instructions](week9.html#preparation). You will also want to install the `lubridate` package using `install.packages("lubridate")`, before following any of the videos below.

### Controlling what happens in your script

Sometimes you want R to do different things depending on the value of an object. We use `if()` statements to do this. Or you might need to repeat a task using a `for()` loop. 

* [Video on if statements plus another function](https://youtu.be/gBRqU9lQi3I)
* [Video on the ifelse() function](https://youtu.be/GgWadLQ9UEw)
* [Video on for loops and date-time objects](https://youtu.be/W4HC6dABZss)
* [More on for!](https://youtu.be/OaEWftFQzaQ)
* [Reading for this lesson](http://swcarpentry.github.io/r-novice-gapminder/10-control-flow.html).

### Plotting error bars

Perhaps the most important thing you can do in Science is quantify how certain you are. In plots we do this with error bars. `ggplot2` has several ways to do error bars. 

* [Video on error bars with ggplot2 stats and geoms](https://youtu.be/K4MgpFXVFqU)
* [Video on adding error bars from external calculations](https://youtu.be/XBtu2o4a8fo)
* [ERRATUM! setting the width when x aesthetic is a date-time object](https://youtu.be/316gyQyV9fE) tl;dw -- the width aesthetic is measured in the same units as the x-axis. For a plot with a date-time object on the x axis that unit is **seconds**!



### Assignment

The file for this weeks assignment will be a commented R script. The file should be saved with a name like `yourlastname_week10.R`, and uploaded as an attachment. At the top of the file write a comment \(start the line with `#`\) with the week number and your name on one line. If none of that makes sense, go watch the start of [the video for subsetting vectors](https://youtu.be/LZB3x6hNZ9M). 

* Do the Advanced Challenge at the bottom of [this page](http://swcarpentry.github.io/r-novice-gapminder/10-control-flow.html). You can either change back to the my_project project created in week 6, or download the gapminder data again into the week9 project. 

I should be able to run your script from the main directory of the project created in week 9 using `source("code/yourlastname_week10.R")` from a clean start of R. To test your code to make sure it works without errors, first click on the Session menu, and choose `Restart R`. Then open your file and click the `source` button in the top right corner. This will load your file and run it; any output to the console is suppressed. Check the date and time of the saved image file to make sure the script ran correctly. 
 
This challenge is due on Friday of Week 10 \(Mar 18\) at 5 pm. Late assignments will receive 
a score of zero unless prior approval is granted.  
