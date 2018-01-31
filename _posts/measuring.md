---
layout: post
title: "The size does not matter - if you are measuring the wrong thing."
date: 2018-01-31
comments: true
mathjax: true
---


**How do you measure how good your model is?** This might seem like a simple question, but the answer is not straight forward. Model validation is one of the most important activities to get right in Data Science and Quantitative Finance. As in all other sciences, running experiments and measuring the results in an unbiased way is really the core of it all. For those of you having a background in science, you sure know how important this is in the lab. The same is present in the "Data Lab".

<p align="center">
  <img width="400" height="200" src="/figs/classification_measure/lewin1.jpg">
</p>

**Why care about performance measuring in Machine Learning?**
Before going into details of how and what to measure - *why* do we need to measure? A scientific result tells us how our experiment went, and what we can conclude from this. In addition, we want the result to be as objective as possible. In both business and academia, we are tempted to tweak our performance metrics in our favor. As a very good rule of thumb, we should always strive for living up to the first principle of science according to the Nobel Prize winner in Physics, Richard Feynman:

> *You must not fool yourself — and you are the easiest person to fool.* 

<p align="center">
  <img width="200" height="200" src="/figs/classification_measure/feynmanrichardpbio.jpg">
</p>


We should even start to investigate performance metrics **before** we start modelling. Why? In AI/Machine Learning, our model is trained with a cost function. This cost determine how it's *learning*; this cost is the incentive program that make the model distinguish between failure and success. Thus, performance metrics are vital for the modelling itself, not only the evaluation of the results. 

In this post, we will keep the Feynman quote in mind when investigating the performance metrics of classification models. We will for simplicity focus on binary classification models in a supervised learning context. Such models are rather intuitive and well suited to problems we often face in both business and academia. 

## Evaluation 101
A binary classification problem is simply the attempt of labeling our observations into two classes. Let's look at a practical example; you are working for an insurance firm. You observe that the churn rate is high on a certain product, meaning the customers are fleeing to other companies. What can you do? It can be hard to know in advance which of the customers who will leave in the future. Given that you have access to relevant data of the customers, you can at least try to construct a model that predicts if current customers will leave your firm, or not. Then the firm can for example call up the clients with a high chance of leaving, offering lower price (Note that in this situation it is useful to account for the expected return of the customer, as well as numerous other details. However, that's another story.).

<p align="center">
  <img width="400" height="200" src="/figs/classification_measure/validation_ml.png">
</p>

In our binary classification problem of churn, we attempt to label "churn" or "no churn", i.e. two options. The convention is to name the labels as "positive" (p) or "negative" (n), in order to be more general. Say we have built a model and we'd like to evaluate it. Then we should use a *unseen* test set of customers, meaning the model has not been trained with this data. However, *we* know the correct labels and can use that to verify how well the model performs. When applying the model on the current customers, we have four possible outcomes per customer:

<p align="center">
  <img width="300" height="220" src="/figs/classification_measure/confusion_matrix_1.png">
</p>

The above figure represents the *confusion matrix*. This summarize the outcome of our binary classification problem. In a binary case, we have four outcomes as explained in the figure; true positive, true negative, false positive and false negative. 

Note that we often deal with models that outputs a range, instead of binary outcomes. The range represents how likely the model considers a certain label to be correct. Let's choose the range to be between 0 and 1. In order to match this with a binary label, we have to introduce a *cut-off*. For example, we can say that all outputs above 0.5 correspond to the positive label, and below correspond to the negative. Thus we have a new dimension to our problem; the cut-off. The cut-off will change the whole confusion matrix, raising and lowering the bar. 

## How to choose the right performance metric(s)?

Let's look at the following example. We test the trained model with a test set consisting of 100 positive observations, and 100 negative observations. We then deal with 200 unseen observations in total, which can be consumers like the stick man George in the figure above. Now things are becoming interesting, since we will need many observations (often it is required much more than 200) to find anything statistical significant about our model performance. Let's consider the following result

<p align="center">
  <img width="300" height="200" src="/figs/classification_measure/conf_matrix_1.png">
</p>

Looking at this table, we see a quite reasonable result. Most of our observations were classified correctly (as true negatives and true positives). The ratio reflecting this is called *accuracy*; the number of correct predictions divided on the total observations. Here, the accuracy is (63+72)/(28+37+63+72) = 67.5 %. We can look into many other simple ratios, for example the sum of true positives divided by the all the actual positives. This is called *true positive rate*, and tell us how well we predict positive observations. 

**But which metric should we use?** They all have their drawbacks... Let's look at some examples in order to illustrate what can go wrong when not paying attention.

<p align="center">
  <img width="300" height="200" src="/figs/classification_measure/skewed.jpg">
</p>

* In some situations, false negatives and false positives are not symmetrically "bad". Say we focus on a virus like Ebola, where we want to construct a model for predicting if a person has the disease or not. Assume also that the hospitals prioritize this issue to a large extent and thus have large capacity. We would be very upset to classify some people as healthy, where they in reality are sick. We don't want to label healthy people as sick, but this is of lower priority. A clever doctor will probably figure this out in later diagnosis. This implies that we should pay more attention to the true positive rate than the accuracy.
<p align="center">
  <img width="400" height="266" src="/figs/classification_measure/pregnant.jpg">
</p>

* We have very skewed data. In anti-money-laundering compliance, the data are generally very skewed. Often (and hopefully) are not too many customers involved in money laundering. If we would evaluate our model in terms of accuracy, we would then have a very high accuracy using a model that's predicting all customers as honest. That number can trick people to think your model is brilliant, but is in reality worth nothing. Such problems can be quite hard to model, since the learning mechanism has rather limited number of the small group examples. There are many techniques to deal with skewness, both from a metric perspective and sampling perspective.

* The observant reader might wonder; what about the *cut-off* mentioned above? The cut-off will influence the whole confusion matrix, and thus its derived ratios too. In fact, all ratios are turned into vectors, where each point on the vector will correspond to a certain cut-off. Plotting these confusion ratios with respect to the cut-off are useful, for example through using the [ROC-curve](https://en.wikipedia.org/wiki/Receiver_operating_characteristic). The perhaps most common practice is to use a derived value from the ROC-curve as the main performance metric of the model, called the [Area under the curve (AUC)](https://en.wikipedia.org/wiki/Receiver_operating_characteristic#Area_under_the_curve).

## Wrap-up

Overall, performance metrics are vital in order to 1: **evaluate your model correctly**, and 2: **train your model to solve the right problem**. We choose our performance metrics through carefully designing our business case and having a good understanding of the underlying data.

The intension in this post was not to give out a recipe of how to measure. Many think that Machine Learning is a simple "plug-in" you can throw data at and out comes a good model. However, there are no free lunch here; the approach and solution must be customized to your problem.

Cheers!


