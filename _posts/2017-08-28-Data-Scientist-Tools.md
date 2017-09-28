---
layout: post
title: "Useful tools for a Data Scientist"
date: 2017-09-28
comments: true
---

Hey there you beautiful ladies and gentlemen, señoras y señores, damen und herren. Hope you are doing fine. In this post, I will write a bit about the different types of tools I am considering to be vital as a Data Scientist. This is a quick read, just to get the basic overview. The three "must-have-in-place-tools" have
* Modelling tool for doing the cool stuff (R & Python)
* Use Git to avoid a mess
* Manage databases in order to…. handle your data!
* Big data frameworks


### Your modelling tool

So, how to do some proper modelling? You use some kind of programming language. There are many options, however I will do some clarifications on what you should NOT choose. Proprietary software is usually a bad choice, compared to open source. Why? 
1. There is a "small" group of people in the firm that has developed it. Even though Microsoft, SAS etc. are huge corporations, there are still many more Python developers out there. Open source makes everyone able to contribute, and yes, there are a horde of bug-fixers among them. Trust people instead of corporations. 
2. With open source you can actually see how your tools are put together. Everyone have access to everything. Thus you can look in all source code to understand what is going on, as well as tuning, fixing and further extend. This makes open source much more secure.
3. Solving problems is completely another story with open source. The resources are just incrediible huge. There are blogs, forums, tutorials, you names it, for everything. I personally get stuck immidiately with a proprietary software. Googling is the way to go, and you often end up at [Stackoverflow](https://stackoverflow.com/), where in April 2014 Stack Overflow had over 4,000,000 registered users.
4. For us, most of the open source tools are also free. Proprietary alternatives are usually damn expensive. 

![center](/figs/2017-08-18-Data-Scientist-Tools/R-vs-Python-Data-Science-machine-learning.jpg)


That being said, I'll mention the appropriate languages for a Data Scientist. The most popular are Python and R. Those are brilliant, due to
1. They are free, open source and quite flexible. You can basically "do anything".
2. They are rather easy, compared to e.g. C++. Python and R are less flexible than e.g. C++ but this is traded off with simplicity, which makes people able to get up to speed very fast.
3. You have so many available libraries, specially those usable for Data Science. R and Python are not really high performance languages, but most underlying functions and libraries are written in some kind of C-languages. Thus, if you leverage the libraries properly, you more or less get C-speed. Avoid doing things like "for-loops" and other computational intensive tasks straight out; use instead the build in functions of the libraries. 

So; R or Python? It doesn't really matter. Python is perhaps more flexible, while R is more speciallized for your core Data Science work. Lastly I quickly mention the key-libraries for each:
* Python : [Pandas](http://pandas.pydata.org/), [scikit-learn](http://scikit-learn.org/stable/sci),  [NumPy](http://www.numpy.org/) and [Matplotlib](https://matplotlib.org/).
* R : [dplyr](https://cran.r-project.org/web/packages/dplyr/index.html), [caret](http://topepo.github.io/caret/index.html) and [ggplot2](http://ggplot2.org/).


### Share and Keep track on your Code - Version Control with Git 

Have you ever changed you code that worked, for so regretting this and longing back to the previous stage? Or just want to see how your code looked like two months ago? Or easily collaborate with other developers ? Git solves all these problems and many more.

To put it straight; Git is a must-have tool for developers for avioding a huge mess. Still, I continue to get suprised of how few developers who actually use it in the industry. I must say that Git is a bit tricky to understand, since it is a different concept than normal saving and file storage. It is a "layer on top of this", so that Git gives you a bit of an inception feeling, a new dimension to what you are familiar with. The workflow below is the one most typical (made by www.git-tower.com).

![center](/figs/2017-08-18-Data-Scientist-Tools/basic-remote-workflow.png)

There are many out there who already have given excellent tutorials on Git, much better than what I can wrap together. Therefore I pass the ball over to some other sources when it comes to usage and undestanding. There are many sources to choose from, but I feel the following book is excellent for learning Git. See [Pro Git book, written by Scott Chacon and Ben Straub](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control), thanks for making this great tutorial.

You can host your repository at Github, like I do with this website. There are many others, like [Gitlab](https://about.gitlab.com/) or [Bitbucket](https://bitbucket.org/). If you get a bit tired of using Git Bash, the Unix Shell, there are some GUI clients for you. A selection of these can be found [here](https://git-scm.com/downloads/guis). Lastly, I highly recommend you to use Diffmerge, an application to visually compare and merge files. You can download it [here](https://sourcegear.com/diffmerge/) and a tutorial to use it with the Sourcetree GUI can be found [here](https://www.youtube.com/watch?v=sIwh4UvApMU).


### Managing data and scalability

#### Databases
Data Scientists work with huge sets of data. If trying to store in normal files (flat files), you soon will end up with a mess. Git is not your way to solve this issue. Here you use databases. We extract data from the databases, often stored at a server (or could be your own laptop, however not very efficient and "impossible" to collaborate). We also build databases and store our data there. There are many options to where the database should be; in a cloud service, a local server, your computer etc. 

Databases have their own languages, Query languages. They all have their pro's and con's, so you choose the one matching your needs. An important thing to get right, is the difference between relational and non-relational databases. In the former, you typically have SQL, the latter you have noSQL such as MongoDB. Alan Perkins gives in this [video](https://www.youtube.com/watch?v=XPqrY7YEs0A) an explanation I like a lot. 



### Big data frameworks

When your data sets grows, at some point it is useful to leverage big data frameworks. I put this as an own section, mostly because it is hard to fit it together with the topics above. The reason is that the big data frameworks involve both processing and data storage. We will now quickly mention the two most popular frameworks, which again are not mutually exclusive. 

* **Hadoop**. This framework consists of several modules, among them we have MapReduce and Hadoop Distributed File System (HDFS). The former is a programming framework, and the latter is for storage. Hadoop is designed to scale up from single servers to thousands of machines, each offering local computation and storage. To scale in such a way, desentralized storage AND using local computation, is really a big deal. 

* **Spark**. This is an open-source cluster-computing framework. As well as MapReduce, does Spark aim to perform data analytics on distributed computing cluster. Spark provides in-memory computations for increase speed and data process over Mapreduce. It is common to use Spark on top of a Hadoop cluster, however this is not a must. Spark runs applications in Hadoop clusters up to 100x faster in-memory and 10x faster on disk, compared to MapReduce. For more of the differences between Spark and MapReduce, check out this [link](https://www.youtube.com/watch?time_continue=11&v=KzFe4T0PwQ8).




