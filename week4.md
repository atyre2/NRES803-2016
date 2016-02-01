---
title: NRES 898 Week 4
layout: page
root: .
venue: "University of Nebraska-Lincoln"      # brief name of host site without address (e.g., "Euphoric State University")
---
## Week 4: Version Control with Git

This week's lessons introduce the concepts of version control using Git. 
[Here's some motivation, including a PhD comic](http://swcarpentry.github.io/git-novice/01-basics.html).
If you have used "track changes" in a word processor, you are already familiar 
with a simple form of version control. Git is a tool that dramatically
expands these capabilities to include any kind of text file. This will be 
particularly useful when working collaboratively on data analysis projects
that use script files for data analysis. 

**NOTE:** you will need to create a free github account in order to follow 
along with some of these lessons, and do the collaboration exercise. 

The page with the index to all lessons, as well as links to additional
resources [is here](http://swcarpentry.github.io/git-novice/).

### Setup up Git and creating a repository

* [Video Tutorial](https://youtu.be/n_N0kxGRjbk)
* [Setup Lesson](http://swcarpentry.github.io/git-novice/02-setup.html)
* [Create repository Lesson](http://swcarpentry.github.io/git-novice/03-create.html)

### Tracking changes, exploring the history and ignoring things

* [Tracking changes](http://swcarpentry.github.io/git-novice/04-changes.html) and
  the [Video Tutorial](https://youtu.be/nJ5e8fRD8zg). Do both challenges on the Tracking changes page. On the bio Repository challenge, paste the results of git diff into your answer file.
* [Explore the history](http://swcarpentry.github.io/git-novice/05-history.html) and
    the [Video Tutorial](https://youtu.be/I_nDUtp6qOM). Do the Recovering Older Versions of a File challenge.
* [Ignoring things](http://swcarpentry.github.io/git-novice/06-ignore.html) and 
    the [Video Tutorial](https://youtu.be/Ff9x_4pLNgo). 

### Remotes 

* [Remote repositories](http://swcarpentry.github.io/git-novice/07-github.html) and the
  [Video Tutorial](https://youtu.be/EaQce6ATJu0)
* Do the GitHub Timestamp challenge on that page.

### Collaboration and conflicts

* We will do this exercise in Tuesday's synchronous session. I will provide a
    handout with step-by-step instructions at that time. You will find it easier
	to follow along if you have already viewed the tutorials, but you need not
	have completed this weeks challenges. The readings below contain additional useful
	background but are also not essential. 
* To prepare for this exercise, you will need to do a couple of steps to get a copy
     of the `planets` repository referred to in the exercise. The following assumes you
	 are in your user directory (or anywhere else you can create files), and if you do 
	 `ls` it does not show a directory called planets. 
	 
     ~~~
	 git clone https://github.com/atyre2/planets-template.git planets
     cd planets
     git remote set-url origin https://github.com/yourusername/planets.git
     git remote -v
     ~~~
	 
	 This copies the repository from my github to your harddrive, and then 
	 changes the remote repository from my github to a repository on your github
	 account. If you try pushing to that repository however, you will discover that 
	 the planets repository is not found. Point your browser to github.com/yourusername 
	 and add a repository named planets. After that you will be able to `git push origin master`
     from the planets directory and it will push the contents to your remote repository.
	 Now you are ready to do the exercises below with a partner. 
* [Collaboration reading](http://swcarpentry.github.io/git-novice/08-collab.html)
* [Resolving conflicts reading](http://swcarpentry.github.io/git-novice/09-conflict.html)
* Run `git log` in *your* planets directory and copy the results to your 
    Challenge Answers file.
	

### Assignment

Challenges are due on Friday of Week 4 \(Feb 5\) at 5 pm. Late assignments will receive 
a score of zero unless prior approval is granted. Your answers should be 
entered into a plain text file. At the top of the file write 
the week number and your name on one line. Leave a blank line, and type the 
name of the lesson. For each challenge in the lesson, on one line, give the 
title of the Challenge. On the next line, enter your answer. This may be 
simply a number in the case of a multiple choice question, or perhaps a couple 
lines of commands or text. Separate challenges with blank lines.