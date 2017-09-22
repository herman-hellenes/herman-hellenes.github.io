---
layout: post
title: "Project Management Part 2 - Agile Development"
date: 2017-08-19
comments: true
---


Hey there you beautiful ladies and gentlemen, señoras y señores, damen und herren, 女士们(們) 先生们(們 ! Hope you have a great day. I am continuing with a posts regarding Project Management of Data Science/Mining projects. In [last post](https://herman-hellenes.github.io/blogposts/CRISP-DM), we discussed the Cross Industry Standard Process for Data Mining (CRISP-DM). CRISP-DM is about defining the different steps we need to go through in a Data Science project. This starts with defining the problem to reaching an operational state. In this manner, CRISP-DM is *what you do*.   In this post, we will discuss *how you do it*, meaning how to work in teams and how we in an effective way get through the CRISP-DM steps. 

A very popular framework for software developers is Agile Development. If you are familiar with Scrum or Lean software development, these concepts are all entangled. These frameworks are suited for development projects, exploring new seas. For now I refere to this whole blob of framework as **Agile**. Before digging into the material; it is not true that Agile is a perfect way to manage a project, it is still really hard to pull it off. We will revisit this later in the post.


### The core concept of Agile

Many books and discussions have already been done on the topic. This post gives only a short intro to the concept, so as a Data Scientist you are aware of this way of working. Due to the framework is widely used, you now will get the main idea of it. To simplify, we can make two categories of how to develop a product.

* Do everything in one go, sequentially.
* Iterative

The Waterfall model, a sequential (non-iterative) design process, is the most used framework for the former point. Agile goes under the latter category. Does that mean that we get a half-done product in the first iteration by applying Agile? Both yes and no. We aim in each iteration to come up with a Minimum Viable Product (MVP). Meaning; it is not the very final product, but it is a product that works, but can in the future be added to it more features and complexity. To give an example: you try to build a car. Instead of building the car in one go, you start with making a skateboard. That is much easier, and you find out that this product actually is something people out there wants. Then you can iterate over to a bike, a scooter and then a car. This may seem like a stupid example, which is true, but this is kind of the concept of Agile. The drawback with the waterfall approach is that you have up front large investments, and it is not flexible such that you can pivot as in the Agile setting. 


![center](/figs/2017-08-19-scrum-agile/agile.jpg)




Working with the CRISP-DM process, we thus start with building a quite simple model based on e.g. expert knowledge or a linear regression model. We will rush through the whole process and learn a lot about the problem and the data. Then we can decide if we want to try an advanced model in the next iteration. 

Eric Rice has written the book [Lean Startup](http://theleanstartup.com/), which describes an iterative way of building companies. Data Scientist involved in startups, as well as internal business development roles, will find his [Lean Startup talk at Google](https://www.youtube.com/watch?v=fEvKo90qBns&t=3s) interesting. I think this one hour intro gives a satisfying explaination of the core concept of Agile / Lean Startup. 



### Team organization with Scrum

So we want to work in an agile way, iterating our product. Scrum is a framework to organize teams of few people, setting up "sprint", which are short periods with a clear deadline. Here, [Jira](https://www.atlassian.com/software/jira) is a quite nice tool.


### Pitfalls

[Why it’s hard to be big and agile](https://www.linkedin.com/pulse/why-its-hard-big-agile-stanislaw-matczak)


