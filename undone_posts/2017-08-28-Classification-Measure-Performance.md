---
layout: post
title: "The size does not matter - if you are measuring the wrong thing."
date: 2018-01-16
comments: true
mathjax: true
---


**How do you measure how good your model is?** This might seem like a simple question. Nevertheless, it is not that straight forward to answer. Model validation is one of the most important thing to get right in Data Science. As in all other sciences, running experiments and measuring the results in an unbiased way, is really the core of it all. For those of you having a background in science, you sure know how important this is in the lab. The same is present in the "Data Lab".

<p align="center">
  <img width="400" height="200" src="/figs/classification_measure/lewin1.jpg">
</p>

**Why care about performance measuring in Machine Learning?**
Before going into details of how and what to measure - *why* do we need to measure? A scientific result tells us how our experiment went, and what we can conclude from this. In addition, we want the result to be as objective as possible. In both business and academia, we are tempted to tweak our performance metrics in our favor. As a very good rule of thumb, we should always strive for living up to the first principle of science according to the Nobel Prize winner in Physics, Richard Feynman:

> *You must not fool yourself — and you are the easiest person to fool.* 

<p align="center">
  <img width="200" height="200" src="/figs/classification_measure/feynmanrichardpbio.jpg">
</p>


We should even start to investigate performance metrics **before** we start modelling. Why? Our model is trained with a cost function; how it's learning really depends on how we tell it to distinguish between failure and success. Thus, performance metrics are vital for the modelling itself, not only the evaluation of the results. 

In this post, we will keep the Feynman quote above in mind when investigating the performance metrics of classification models. Binary 
classification models, to be precise, in a supervised learning context. Such models are rather intuitive and well suited to problems we often face in both business and academia. 

## Evaluation 101
First, a binary classification problem is simply the attempt of labeling our observations into two classes. As a practical example, say you are working for an insurance firm. You observe that the churn rate is high on a certain product, meaning the customers are fleeing to other companies. What can you do? It can be hard to know in advance which of the customers who will leave in the future. Given that you have access to relevant data of your customers, you can at least try to construct a model that predicts if current customers will leave your firm, or not. Then the firm can e.g. call up the clients with a high chance of leaving and offer them a lower price. (Note that in this situation it is useful to account for the expected return from the customer, as well as numerous other details. However, that's another story.)

<p align="center">
  <img width="400" height="200" src="/figs/classification_measure/validation_ml.png">
</p>

In our binary classification problem of churn, we attempt to label "churn" or "no churn", i.e. two options. The convention is to name the labels as "positive" (p) or "negative" (n), in order to be more general. Say we have built a model and we'd like to evaluate it. Then we should use a *unseen* test set of customers, meaning the model has not been trained with this data. However, we know the correct labels and can then verify how well the model performs. When applying the model on the current customers, we have four possible outcomes per customer:

<p align="center">
  <img width="300" height="200" src="/figs/classification_measure/confusion_matrix_1.png">
</p>

The above figure represents the *confusion matrix*, which summarize up the outcome of our binary classification problem. In a binary case, we have four outcomes as explained in the figure; true positive, true negative, false positive and false negative. 

Note that we often deal with models that outputs a range, instead of binary outcomes. The range represents how likely the model considers a certain label to be correct. Let's choose the range to be between 0 and 1. In order to match this with a binary label, we have to introduce a *cut-off*. For example, we can say that all outputs above 0.5 correspond to the positive label, and below correspond to the negative. Thus we have a new dimension to our problem; the cut-off. The cut-off will change the whole confusion matrix, raising and lowering the bar. 

## How to choose the right performance metric(s)?

Let's do an example. Say we try to test the model with 100 positive observations, and 100 negative observations. We then deal with 200 unseen observations in total, which can be consumers like George in the figure above. Now things are becoming interesting, since we will need many observations (often it is required much more than 200) to find anything statistical significant about our model performance. Let's consider the following result

<p align="center">
  <img width="300" height="200" src="/figs/classification_measure/conf_matrix_1.png">
</p>

Looking at this table, we see a quite okay result. Most of our observations were classified correctly (as true negatives and true positives). The ratio reflecting this is called *accuracy*; the number of correct predictions divided on the total observations. Here, the accuracy is (63+72)/(28+37+63+72) = 67.5 %. We can look into many other simple ratios, for example the sum of true positives divided by the all the actual positives. This is called *true positive rate*, and tell us how well we predict positive observations. 

**But which metric should we use?** They all have their drawbacks... Let's look at some examples in order to illustrate how wrong things can turn out when not paying attention.

<p align="center">
  <img width="300" height="200" src="/figs/classification_measure/skewed.jpg">
</p>

1. In some situations, false negatives and false positives are not symmetrically "bad". Say we have an epidemic going, and we want to make a model for predicting if a person has the disease or not. If the medical system has good capacity and take this problem very seriously, we would be very upset to classify some people as healthy, where they in reality are sick. We don't want to label healthy people as sick, but this is of lower priority. A clever doctor will probably figure this out in later diagnosis. This implies that we should pay more attention to the true positive rate than the accuracy.

<p align="center">
  <img width="400" height="266" src="/figs/classification_measure/pregnant.jpg">
</p>

2. We have very skewed data. In anti-money-laundering programs, the data often turn out skewed. Often (and hopefully) are not too many customers involved in money laundering. Then we can end up having e.g. over 90 % of the label corresponding to honest customers. If we would evaluate our model in terms of accuracy, we would have 90 % accuracy with a model that's predicting all customers as honest. That number can trick people to think your model is brilliant, but is in reality worth nothing. 

3. The observant reader might wonder; what about the *cut-off* mentioned above?? The cut-off will influence the whole confusion matrix, and thus also the derived ratios. In fact, all ratios are turned into vectors, where each point on the vector corresponds to a certain cut-off. Plotting these confusion ratios with respect to the cut-off are useful, for example through using the [ROC-curve](https://en.wikipedia.org/wiki/Receiver_operating_characteristic). The perhaps most common practice is to use a derived value from the ROC-curve as the main performance metric of the model, called the [Area under the curve (AUC)](https://en.wikipedia.org/wiki/Receiver_operating_characteristic#Area_under_the_curve).

## Wrap-up

Overall, performance metrics are vital in order to 1: **evaluate your model correctly**, and 2: **train your model to solve the right problem**. Moreover, how do we know which to pick? Through carefully designing your business case and investigating the data.

It was not the intension to give out a recipe of how to measure in this post. Many think that Machine Learning is a simple "plug in" you can throw data at, and out comes a good model. However, there are no free lunch; the approach and solution must be customized your problem.

Cheers!


