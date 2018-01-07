---
layout: post
title: "Why care about performance measuring in Machine Learning ?"
date: 2018-01-4
comments: true
mathjax: true
---


How do you measure how good your model is? This might seem like a simple question. But it is not that straight forward to answer. Model validation is one of the most important thing to get right in Data Science. As in all other sciences, running experiments and measuring the results in an unbiased way, is really the core of it all. For those of you having a background in science, you sure know how much effort that is put into this in the lab. The same is present in the "Data Lab".

<p align="center">
  <img width="400" height="200" src="/figs/classification_measure/lewin1.jpg">
</p>


Before going into details of how and what to measure, *why* do we need to measure? A scientific result aims to tell us, in an objective way, how our experiment went and what we can conclude from this. Both in business and academia, we are tempted to tweak our performance metrics in our favour. As a very good rule of thump, we should always strive for living up to the first principle of science according to the Nobel Prize winner in Physics, Richard Feynman

> *You must not fool yourself — and you are the easiest person to fool.* 

In this post, we will keep this quote in mind when investigating the performance metrics of classification models. Binary 
classification models, to be precise, in a supervised learning context. Such models are rather intuitive and well suited to problems we often face in both business and academia. 

## Confusion Matrix
First of all, a binary classification problem is simply attempt labeling each of your observations into two classes. As a practical example, say you are working for an insurance firm. You observe that the churn is high on a certain product, without there being some very obious reason for this. Given that you have access to relevant data of your customer, you can construct a model that predicts that the current costumers will leave your firm, or not. This should then be used to do some action; for instance to call up the clients with a high chance of leaving and offer them a lower price. Note: in this situation it is useful to account for the expected return from the customer as well as numerous other details, but that is another story.


<p align="center">
  <img width="400" height="200" src="/figs/classification_measure/validation_ml.png">
</p>

In our binary classification problem we attempt to lable "churn" or "no churn", namly two options. The convension is to rather say "positive" (p) or "negative" (n), in order to be more general. So say you have build a model you would like to evaluate. We take a *unseen* test set of customers, meaning the model has not seen this data before, but we sit with the correct lables to verify how well the model perform. When applying the model on the current customers, we have four possible outcomes per customer:

<p align="center">
  <img width="400" height="200" src="/figs/classification_measure/confusion_matrix_1.png">
</p>

The above figure represent the *confusion matrix*, which summarize up the outcome of our the binary classification problem. Note that we often deal with a model that outputs a range of how likely it consider a certain lable to be correct. Let us choose this range to be between 0 and 1. In order to match this with a binary label, we have to introduce a *cut-off*. For example, we can say that all outputs above 0.5 correspond to the positive label, and below correspond to the negative. Thus we have a new dimension to our problem; the cut-off. How we choose this cut-off is important we will see later on.

## Performance measures based on the confusion matrix

Back to the confusion matrix; say we try to test the model with 100 positive observations, and 100 negative observations. In total we then deal with 200 unseen observations, that for example can be consumers like George as in the figure above. Now things are becoming interesting, since we will need a lot of observations (often much more than 200) to find anything statistical significant about our model performance. Let's consider the following result

<p align="center">
  <img width="300" height="200" src="/figs/classification_measure/conf_matrix_1.png">
</p>

Looking at this table, we see a quite okay result. Most of our observations was classified correct, meaning as either true negatives or true positives. This ratio we speak of is called *accuracy*, the number of correct predictions divided on the total observations, which here is (63+72)/(28+37+63+72) = 67.5 %. Further we can look into many other simple rations, for example the sum of true positives divided by the all the actual positives. This is called *true positive rate*, and tell you how well you predict positive observations. 

**But which metric should we use?** They all have their drawbacks... Let's look at some examples in order to illustrate how wrong things can turn out when not paying attention.

1. In some situations, false negatives and false positives are not symmetrically "bad". Say we have a epedemic going, and we have made a model for predicting if persons has the deciece given sympthomas, age, geography etc. If the medical system has good capacity and take this problem very seriosly, we would be very upset to classify some people as healty, where they in reality are sick. On the other hand, it is the secondary priority to not lable in reality healthy people as sick, which will hopefully be reveiled in later diagnosis. In such situation it is helpful to for example look at the true positive rate.

2. We have very skewed data. In looking credit risk, or anti-money-laudering,  When dealing with  skewed data
3: very high/low cutoffs --> and how to find this cutoff?

## How to select a good performance metric ?

Depends on your problem!



HERMAN: say that I get going some more posts, especially on imbalanced distributions. and here I cover the "basics", there go into spesific case
