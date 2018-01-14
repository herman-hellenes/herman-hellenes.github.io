---
layout: post
title: "The size does not matter, if you are measuring the wrong thing"
date: 2018-01-4
comments: true
mathjax: true
---


**How do you measure how good your model is?** This might seem like a simple question. But it is not that straight forward to answer. Model validation is one of the most important thing to get right in Data Science. As in all other sciences, running experiments and measuring the results in an unbiased way, is really the core of it all. For those of you having a background in science, you sure know how much effort that is put into this in the lab. The same is present in the "Data Lab".

<p align="center">
  <img width="400" height="200" src="/figs/classification_measure/lewin1.jpg">
</p>

**Why care about performance measuring in Machine Learning?**
Before going into details of how and what to measure, *why* do we need to measure? A scientific result aims to tell us, in an objective way, how our experiment went and what we can conclude from this. Both in business and academia, we are tempted to tweak our performance metrics in our favour. As a very good rule of thump, we should always strive for living up to the first principle of science according to the Nobel Prize winner in Physics, Richard Feynman:

> *You must not fool yourself — and you are the easiest person to fool.* 

<p align="center">
  <img width="400" height="200" src="/figs/classification_measure/feynmanrichardpbio.jpg">
</p>


We should start on investigating performance metrics **before** we start modelling. Why? Our model is trained with a cost function; how it is learning really depend on how we tell it to distinguish between failure and success. Thus, this is all vital for the modelling itself, not only the evaluation of the results. 

In this post, we will keep the Feynman quote in mind when investigating the performance metrics of classification models. Binary 
classification models, to be precise, in a supervised learning context. Such models are rather intuitive and well suited to problems we often face in both business and academia. 

## Evaluation 101
First of all, a binary classification problem is simply attempt labeling each of your observations into two classes. As a practical example, say you are working for an insurance firm. You observe that the churn is high on a certain product, without there being some very obious reason for this. Given that you have access to relevant data of your customer, you can construct a model that predicts that the current costumers will leave your firm, or not. This should then be used to do some action; for instance to call up the clients with a high chance of leaving and offer them a lower price. Note: in this situation it is useful to account for the expected return from the customer as well as numerous other details, but that is another story.


<p align="center">
  <img width="400" height="200" src="/figs/classification_measure/validation_ml.png">
</p>

In our binary classification problem of churn, we attempt to lable "churn" or "no churn", namly two options. The convension is to rather say "positive" (p) or "negative" (n), in order to be more general. Say we have build a model and we like to evaluate it. Then we should use a *unseen* test set of customers, meaning the model has not seen this data before. However we know with the correct lables to verify how well the model perform. When applying the model on the current customers, we have four possible outcomes per customer:

<p align="center">
  <img width="300" height="200" src="/figs/classification_measure/confusion_matrix_1.png">
</p>

The above figure represents the *confusion matrix*, which summarize up the outcome of our the binary classification problem. In a binary case, we have four outcomes as explained in the figure; true positive, true negative, false positive and false negative. 

<p align="center">
  <img width="300" height="200" src="/figs/classification_measure/pregnant.jpg">
</p>

Note that we often deal with a model that outputs a range, instead of binary outcomes. The range then represent how likely the model consider a certain lable to be correct. Let's choose this range to be between 0 and 1. In order to match this with a binary label, we have to introduce a *cut-off*. For example, we can say that all outputs above 0.5 correspond to the positive label, and below correspond to the negative. Thus we have a new dimension to our problem; the cut-off. The cut-off will change the whole confusion matrix, raising and lowering the bar. 

## How to choose the right performance metric(s)?

Let's do an example. Say we try to test the model with 100 positive observations, and 100 negative observations. In total we then deal with 200 unseen observations, that for example can be consumers like George as in the figure above. Now things are becoming interesting, since we will need a lot of observations (often it is required much more than 200) to find anything statistical significant about our model performance. Let's consider the following result

<p align="center">
  <img width="300" height="200" src="/figs/classification_measure/conf_matrix_1.png">
</p>

Looking at this table, we see a quite okay result. Most of our observations was classified correct, meaning as either true negatives or true positives. This ratio we speak of is called *accuracy*, the number of correct predictions divided on the total observations, which here is (63+72)/(28+37+63+72) = 67.5 %. Further we can look into many other simple rations, for example the sum of true positives divided by the all the actual positives. This is called *true positive rate*, and tell you how well you predict positive observations. 

**But which metric should we use?** They all have their drawbacks... Let's look at some examples in order to illustrate how wrong things can turn out when not paying attention.

<p align="center">
  <img width="300" height="200" src="/figs/classification_measure/skewed.jpg">
</p>

1. In some situations, false negatives and false positives are not symmetrically "bad". Say we have a epedemic going, and we have made a model for predicting if persons has the deciece given sympthomas, age, geography etc. If the medical system has good capacity and take this problem very seriosly, we would be very upset to classify some people as healty, where they in reality are sick. On the other hand, it is the secondary priority to not lable in reality healthy people as sick, which will hopefully be reveiled in later diagnosis. In such situation it is helpful to for example look at the true positive rate.

2. We have very skewed data. When investigating credit risk or anti-money-laundering, the data often turn out skewed. Hopefully, not many bank customers are doing money laundering. Then we can end up having over 90 % of the lable corresponding to honest customers. If we would evaluate our model in terms of accuracy, we would have 90 % accuracy with a model just predicting all customers as honest. That is no value added data science work.

3. The observant reader might wonder; what about the *cut-off*?? The cut-off will influence the whole confusion matrix, and thus also the derived ratios. In fact, all ratios are turned into vectors, where each point on the vector correspond to a cut-off. Plotting confusion ratios with respect to the cut-off is then useful, for example through using the (ROC-curve)[https://en.wikipedia.org/wiki/Receiver_operating_characteristic].

## Wrapup

All in all; performance metrics are vital in order to 1. evaluate your model correctly, and 2. train your model to solve the right problem. And how do we know? Through knowing your business case and data. There are no free lunch here, and it all depends on your problem.

Cheers!
