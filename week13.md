---
title: NRES 898 Week 13
layout: page
root: .
venue: "University of Nebraska-Lincoln"      # brief name of host site without address (e.g., "Euphoric State University")
---

## Week 13: Data entry/organization in spreadsheets

See [the bottom of this page](#assignment) for this weeks Challenge. 

### Preparation

This week's videos and exercises are based on educational materials from the [DataONE project](https://www.dataone.org). We will do a little bit of R, so create a new project in RStudio for week 13. The data files needed for the challenge can be [downloaded here](https://www.dataone.org/sites/all/documents/DataFiles_L04L05L07L08.zip) as a zip archive. Extract the files into the data subdirectory of your RStudio project directory. These are Microsoft Excel files, so cannot be directly read into R \(easily\). Part of this weeks challenge is getting the data into R so you can make some plots!

### Introduction to data management: why worry?

* [Video introduction](https://youtu.be/hgt-rhnLZ6g)
* [One page handout for this lesson](https://www.dataone.org/sites/all/documents/L01_DataManagement_Handout_FINAL.pdf).
* [Some additional thoughts on the data life cycle](http://atyre2.github.io/sampling-novice/01-sampling.html). Keith Hurley's data lifecycle is simpler than DataONE!

### Tidy data and data validation

There are good ways to put your data in a spreadsheet. Hadley Wickham \(author of dplyr and ggplot2\) calls these "tidy data".

* [Video with DataONE examples of untidy and tidy data](https://youtu.be/41XhdFMKA3E)
* [Video on tools to validate data](https://youtu.be/ym0ARDJyKtU)
* [Video demo of using data validation in Excel](https://youtu.be/sNSPPlLdRf8)
* [One page handout on tidy data and validation](https://www.dataone.org/sites/all/documents/L04_DataEntryManipulation_Handout_FINAL.pdf) 
* [Hadley Wickham's Tidy data paper](http://vita.had.co.nz/papers/tidy-data.pdf)

### Quality Assurance / Quality Control for data

* [Video on QA/QC](https://youtu.be/0tHH_VuRJ0k)
* [One page handout](https://www.dataone.org/sites/all/documents/L05_DataQualityControlAssurance_Handout_FINAL.pdf)

### Assignment

This weeks assignment has some plain text writing. Please write this in a text editor, and copy/paste it into the Bb submission area. You have to click "Write Submission" next to the "text submission"; it is directly above the attach submission button. If you enter your assignment into the comments box it is difficult for me to extract. 

You will also attach a commented R script. The file should be saved with a name like `yourlastname_week13.R`, and uploaded as an attachment. At the top of the file write a comment \(start the line with `#`\) with the week number and your name on one line. If none of that makes sense, go watch the start of [the video for subsetting vectors](https://youtu.be/LZB3x6hNZ9M). 

* Open the 3 Excel files downloaded above and inspect them.  Based on what you have learned so far about data management, what are some problems in the way the data are currently organized, and how could you fix them? 
* Examine each of the files using the quality assurance strategies described above. Describe all the problems you identify in the text submission. 
* Choose one of the files, import it into R, and repeat the quality assurance steps using R code \(e.g. looking at head() or tail() of data sorted by different columns, plotting\). Document your actions in an R script that you attach to this weeks assignment. 

I won't be able to run this week's script because the steps you took in Excel to make the data readable in R will differ from what I might have done. But I still want to see what you tried.  
 
This challenge is due on Friday of Week 13 \(April 8\) at 5 pm. Late assignments will receive 
a score of zero unless prior approval is granted.  
