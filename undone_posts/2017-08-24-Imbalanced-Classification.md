---
layout: post
title: "How to deal with Imbalanced Classification Problems in Machine Learning"
date: 2017-08-24
comments: true
---


## Setting the stage 

With the free open source libraries for Machine Learning (ML), e.g. Python's scikit-learn and R's caret, predictive analytics is easy and accessible for all. However, deploying the methods "off-the-shelf" does not always lead to success. In this post, we take a look at the problems arising in when dealing with imbalanced distributed data sets in classification problems. As well, we dig into how we can deal with it.

We experience that our ML algorithms struggle when applied on imbalanced classification data sets. Often, we end up with biased predictions and misleading accuracies. This is a result of an algorithm which does not get enough information about the minority class, such that it can make good and accurate predictions. 

First, we elaborate on what an imbalanced distributed data set is, and why ML algorithms face a hard time doing predictions on this type of data. Further we look at how should we can improve our ML techniques in order to give good predictions.  



## Defining Imbalanced Distributed Data and why ML face hard times dealing with it

By doing classification on imbalanced distributed data, we have Imbalanced classification. That is a supervised learning problem, where one class has a much high frequency than the other class(es). Here, the class is what we aim to predict. Let's give an example of this: consider we have all kinds of data on ten thousand insurance customers. We aim to use the data to predict insurance fraud in a supervised learning problem, using binary classification. The classes are then "fraud" and "not fraud". Hopefully for the customer's insurance firm, fraud happens rather seldom. Say 1 % of the customers are abusing the firm, then we are left with only 100 customers in the minority class. Now, we have an imbalaced classification problem. 

So why does the smart ML algorithms struggle with imbalanced classification ? When we use "off-the-shelf"-algorithms, they come with default parameters. Usually they are set to assume balanced classification. This means in practise that the algorithm assumes that errors obtained from different classes have same cost. The algorithms are accuracy driven i.e. they aim to minimize the overall error to which the minority class contributes very little. Then, we end up in a situation where we get biased towards majority class. Again this leads to poor accuracy because of the unequal distribution in dependent variable, when using the appropriate evaluation metric. With imbalanced classification, we must be careful how we measure performance. Recall the above insurance fraud example. We get a 90 % accuracy if we predict every customer as a "not fraud" customer. Not thinking about the imbalaced classes, one might draw the conclusion: this is a quite good prediction, 90 % ! However, if we look at the ratio of true predictions of fraud, we get a hitrate of 0 %. 

To wrap up what we will look at in this post is that
* We must carefully choose our metric, accounting for having imbalanced classification
* We must carefully select model parameters suited for impalanced classification
* Lastly, we have Resampling Techniques. An option is that we can tweak our dataset to be more balanced. 




## Final evaluation metrics
(see Whttps://www.analyticsvidhya.com/blog/2016/03/practical-guide-deal-imbalanced-classification-problems/)

Which performance metrics should we use to evaluate our model ? First, we look into the Confusion Matrix (insert fig). 



# 
# Choosing a performance metric is a critical aspect of working with imbalanced data. Most classification algorithms calculate accuracy based on the percentage of observations correctly classified. With imbalanced data, the results are high deceiving since minority 
# classes hold minimum effect on overall accuracy.

  # ROC
  # There may be situations when ROC fails to deliver trustworthy performance. It has few shortcomings such as.
  # 
  # It may provide overly optimistic performance results of highly skewed data.
  # It does not provide confidence interval on classifier's performance
  # It fails to infer the significance of different classifier performance.

  # Precision: It is a measure of correctness achieved in positive prediction i.e. of observations labeled as positive, how many are actually labeled positive.
  # Precision = TP / (TP + FP)
  # 
  # Recall: It is a measure of actual observations which are labeled (predicted) correctly i.e. how many observations of positive class are labeled correctly. It is also known as 'Sensitivity'.
  # Recall = TP / (TP + FN)




## Model Parameters

### Cost Sensitive Learning
See https://www.analyticsvidhya.com/blog/2016/03/practical-guide-deal-imbalanced-classification-problems/
In simple words, this method evaluates the cost associated with misclassifying observations.
It does not create balanced data distribution. Instead, it highlights the imbalanced learning problem by using cost matrices which describes the cost for misclassification in a particular scenario. Recent researches have shown that cost sensitive learning have many a times outperformed sampling methods. Therefore, this method provides 
likely alternative to sampling methods.




## Resampling Techniques

Below are the methods used to treat imbalanced datasets:

### Undersampling
It reduces the number of observations from majority class to make the data set balanced. This method is best to use when the data set is huge and reducing the number of training samples helps to improve run time and storage troubles.

Undersampling methods are of 2 types: Random and Informative.

R-package: ROSE (Random Over Sampling Examples) package (install.packages("ROSE")). Try out ROSE::ovun.sample (method = "under")

### Oversampling
It replicates the observations from minority class to balance the data. 
An advantage of using this method is that it leads to no information loss. The disadvantage of using this method is that, since oversampling simply adds replicated observations in original data set, it ends up adding multiple observations of several types, thus leading to overfitting. Although, the training accuracy of such data 
set will be high, but the accuracy on unseen data will be worse.

R-package: ROSE (Random Over Sampling Examples) package (install.packages("ROSE")). Try out ROSE::ovun.sample (method = "over")

As well, we can actually trade off with doing both over- and undersampling: Try out ROSE::ovun.sample (method = "both")

### Synthetic Data Generation
In simple words, instead of replicating and adding the observations from the minority class, it overcome imbalances by generates artificial data. It is also a type of oversampling technique.

* The data generated from oversampling have expected amount of repeated observations. 
* Data generated from undersampling is deprived of important information from the original data. 
* This leads to inaccuracies in the resulting performance. To encounter these issues, ROSE helps us to 
generate data synthetically as well. The data generated using ROSE is considered to provide better estimate 
of original data.
* ex: data.rose <- ROSE(cls ~ ., data = hacide.train, seed = 1)$data
* This package also provide us methods to check the model accuracy using holdout and bagging method. This helps us to ensure that our resultant predictions doesn't suffer from high variance.


## Resource library
<https://www.analyticsvidhya.com/blog/2016/03/practical-guide-deal-imbalanced-classification-problems/>
<http://dpmartin42.github.io/blogposts/r/imbalanced-classes-part-1>
<http://dpmartin42.github.io/blogposts/r/imbalanced-classes-part-2>
<http://pages.cs.wisc.edu/~jdavis/davisgoadrichcamera2.pdf> The Relationship Between Precision-Recall and ROC Curves
<http://people.inf.elte.hu/kiss/11dwhdm/roc.pdf>An introduction to ROC analysis
<http://journals.plos.org/plosone/article?id=10.1371/journal.pone.0118432>: The Precision-Recall Plot Is More Informative than the ROC Plot When Evaluating Binary Classifiers on Imbalanced Datasets
<https://topepo.github.io/caret/subsampling-for-class-imbalances.html>
<https://en.wikipedia.org/wiki/Information_retrieval#Mean_average_precision>
<https://www.analyticsvidhya.com/blog/2016/03/practical-guide-deal-imbalanced-classification-problems/>


# TODO 2
# Try instead of AUC the logloss
# https://datascience.stackexchange.com/questions/16232/in-xgboost-would-we-evaluate-results-with-a-precision-recall-curve-vs-roc

