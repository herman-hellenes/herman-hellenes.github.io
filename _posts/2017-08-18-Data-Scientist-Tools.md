---
layout: post
title: "Useful tools for a Data Scientist - Which, and How to get startet?"
date: 2017-08-18
---

Hey there you beautiful ladies and gentlemen, señoras y señores, damen und herren, 女士们(們) 先生们(們 ! Hope everything is going well you you. In this post, I will write a bit about the different types of tools I am considering to be vital as a Data Scientist. This is a quick read, just to get the basic overview. The three "must-have-in-place-tools" have
* Modelling tool for doing the cool stuff (R & Python)
* Use Git to avoid doing the horrible stuff
* Manage databases in order to.... handle your data!


### Your modelling tool

So, how to do some proper modelling? You use some kind of programming languaage. There are many options, however I will do some clarifications on what you should not choose. Proprietary software is usually a very bad choice, compared to open source. Why? 
1. There is a "small" group of people in the firm that have developed it. Even though for instance Microsoft, SAS etc. are huge, there are still many more Python developers out there. Open source makes everyone able to contribute, and yes, there are a horde of bug-fixers among them. Trust people instead of corporations. 
2. With open source you can actually see how it's put together. Everyone have access to everything. Thus you can look in all source code to understand what is going on, as well as tuning, fixing and further extend stuff.
2. Solving problems is completely another story with open source. The resources are just so incrediible huge. There are blogs, forums, tutorials, you names it, for everything. I personally get stuck immidiately with a proprietary software. Googeling is the way to go, and you often end up at [Stackoverflow](https://stackoverflow.com/), where in April 2014 Stack Overflow had over 4,000,000 registered users.
1. For us, most of the open source tools are also free. Proprietary alternatives are usually damn expensive. 

![center](/figs/2017-08-18-Data-Scientist-Tools/R-vs-Python-Data-Science-machine-learning.jpg)


That being said, I'll mention the appropriate languages for a Data Scientist. The most popular are Python and R. Those are brilliant, due to
1. They are open source, and very flexible. You can basically "do anything".
2. They are rather easy, compared to e.g. C++. As well are they less flexible on the low-level scale and slower. 
3. You have so many available libraries, specially those usable for Data Science. Referring to the point above, that R and Python are not really high performance languages, most underlying functions and libraries are written in some kind of C-languages. Thus, if you leverage the libraries properly, you more or less get C-speed. Avoind doing things like "for-loops" and other computational task straight out, use instead the build in functions of the libraries.

So; R or Python? It doesn't matter. Python is perhaps more flexible, while R is more speciallized for your core Data Science work. Lastly I quickly mention the key-libraries for each:
* Python : [Pandas](http://pandas.pydata.org/), [scikit-learn](http://scikit-learn.org/stable/sci),  [NumPy](http://www.numpy.org/) and [Matplotlib](https://matplotlib.org/).
* R : [dplyr](https://cran.r-project.org/web/packages/dplyr/index.html), [caret](http://topepo.github.io/caret/index.html) and [ggplot2](http://ggplot2.org/)

### Share and Keep track on your Code - Version Control with Git for Beginners

Have you ever changed you code that worked, for so regretting this and longing back to the previous stage? Or just want to see how your code looked like a month a go? Or easily collaborate with other developers ? Git solves all these problems, and many more.

To put it straight; Git is a must-have tool for developers for avioding a huge mess. Still, I continue to get suprised of how few who actually uses it within the industry. I must say that Git is a bit tricky to understand, since it is different from just normal saving and file storage. It is a "layer on top of this", so that Git gives you a bit of an inception feeling, a new dimension to what you are familiar with. The workflow below is the one most typical (made by www.git-tower.com).

![center](/figs/2017-08-18-Data-Scientist-Tools/basic-remote-workflow.png)

There are many out there who already have given excellenet tutorials on Git, and much better than what I can wrap together. Therefore I pass the ball over to some other sources when it comes to usage and undestanding. There are many sources to choose from, but I feel the following book to be the best way of learning Git. See [Pro Git book, written by Scott Chacon and Ben Straub](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control), thanks for making this great tutorial.




### Managing databases

Data Scientist work with huge sets of data. If trying to store in normal files (flat files), you soon ending up with a a huge mess. Git is not your way to solve this, but by using databases instead. We extract data from the databases, often stored at a server (or could be your own laptop, however not very efficient and "impossible" to collaborate). We also build databases and store our data there. There are many options for where the database should be; in a cloud service, a local server, your computer etc. 

Databases have their own languages, Query languages. They all have their pro's and con's, so you choose the one matching your needs the most. An important thing to get right, is the difference between relational and non-relational databases. In the former, you typically have SQL, the latter you have noSQL such as MongoDB. Alan Perkins gives in this [video](https://www.youtube.com/watch?v=XPqrY7YEs0A) an explanation I like a lot. 






