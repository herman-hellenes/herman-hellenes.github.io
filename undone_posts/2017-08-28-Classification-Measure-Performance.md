---
layout: post
title: "Art of Measuring your Model"
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
classification models, to be precise. Such models are rather intuitive and well suited to problems we often face in both business and academia. 

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

## Ratios from the confusion matrix

Back to the confusion matrix; say we try to test the model with 100 positive observation, and 100 negative observations. In total we then deal with 200 costumers, like George, as in the figure above. Now things are becoming interesting, since we will need a lot of observations to find anything statistical significant about our model performance. Let's consider the following result

<p align="center">
  <img width="300" height="200" src="/figs/classification_measure/conf_matrix_1.png">
</p>

Looking at this table, we see a quite okay result. Most of our observations was classified correct, meaning as either true negatives or true positives. This ratio we speak of is called *accuracy*, the number of correct predictions divided on the total observations, which here is (63+72)/(28+37+63+72) = 67.5 %. Further we can look into many other simple rations, for example the sum of true positives divided by the all the actual positives. This is called *true positive rate*, and tell you how well you predict positive observations. 

But which metric should we use? They all have their drawbacks... Let's look at some more examples, to illustrate how wrong things can turn out when not paying attention...

1: use accuracy when it is very crucial to not get false negatives (somebody dies)
2: skewed data
3: very high/low cutoffs --> and how to find this cutoff?

## How to select a good performance metric ?

Depends on your problem!



## Receiver operating characteristic (ROC), Area Under Curve, and other plots.
Resources
* Best article: https://en.wikipedia.org/wiki/Receiver_operating_characteristic : 
"In statistics, a receiver operating characteristic curve, i.e. ROC curve, is a graphical plot that illustrates the 
diagnostic ability of a binary classifier system as its discrimination threshold is varied.
The ROC curve is created by plotting the true positive rate (TPR) against the false positive rate (FPR) at various threshold settings.

A ROC space is defined by FPR and TPR as x and y axes, respectively, which depicts relative trade-offs between true 
positive (benefits) and false positive (costs). Each prediction result or instance of a confusion matrix represents one point in the
ROC space.

The best possible prediction method would yield a point in the upper left corner or coordinate (0,1) 
of the ROC space, representing 100% sensitivity (no false negatives) and 100% specificity (no false positives). 
The (0,1) point is also called a perfect classification. A random guess would give a point along a diagonal line
(the so-called line of no-discrimination) from the left bottom to the top right corners (regardless of the 
positive and negative base rates). An intuitive example of random guessing is a decision by flipping coins.
As the size of the sample increases, a random classifier's ROC point migrates towards the diagonal line. In the 
case of a balanced coin, it will migrate to the point (0.5, 0.5).

The diagonal divides the ROC space. Points above the diagonal represent good classification results (better than random), 
points below the line represent poor results (worse than random). Note that the output of a consistently poor predictor 
could simply be inverted to obtain a good predictor.

In binary classification, the class prediction for each instance is often made based on a continuous random variable
{\displaystyle X} X, which is a "score" computed for the instance (e.g. estimated probability in logistic regression). 
Given a threshold parameter {\displaystyle T} T,
the instance is classified as "positive" if {\displaystyle X>T} X>T, and "negative" otherwise. {\displaystyle X} X 
 follows a probability density {\displaystyle f_{1}(x)} f_{1}(x) if the instance actually belongs to class "positive",
 and {\displaystyle f_{0}(x)} f_{0}(x) if otherwise. Therefore, the true positive rate is given by
 {\displaystyle {\mbox{TPR}}(T)=\int _{T}^{\infty }f_{1}(x)\,dx} {\mbox{TPR}}(T)=\int _{T}^{\infty }f_{1}(x)\,dx and 
 the false positive rate is given by
 {\displaystyle {\mbox{FPR}}(T)=\int _{T}^{\infty }f_{0}(x)\,dx} {\mbox{FPR}}(T)=\int _{T}^{\infty }f_{0}(x)\,dx. 
 The ROC curve plots parametrically TPR(T) versus FPR(T) with T as the varying parameter.
 
 
 ### AUC
 When using normalized units, the area under the curve (often referred to as simply the AUC) is equal to the probability that a classifier will rank a randomly chosen positive instance higher than a randomly chosen negative one (assuming 'positive' ranks higher than 'negative').[10] This can be seen as follows: the area under the curve is given by (the integral boundaries are reversed as large 
 T has a lower value on the x-axis)
{\displaystyle A=\int _{\infty }^{-\infty }{\mbox{TPR}}(T)\left(-{\mbox{FPR}}'(T)\right)\,dT=\int _{-\infty }^{\infty }\int _{-\infty }^{\infty }I(T'>T)f_{1}(T')f_{0}(T)\,dT'\,dT=P(X_{1}>X_{0})} {\displaystyle A=\int _{\infty }^{-\infty }{\mbox{TPR}}(T)\left(-{\mbox{FPR}}'(T)\right)\,dT=\int _{-\infty }^{\infty }\int _{-\infty }^{\infty }I(T'>T)f_{1}(T')f_{0}(T)\,dT'\,dT=P(X_{1}>X_{0})}
where {\displaystyle X_{1}} X_{1} is the score for a positive instance and {\displaystyle X_{0}} X_{0} is the score for a negative instance.

#### Drawback AUC
The machine learning community most often uses the ROC AUC statistic for model comparison.[16] However, this practice has recently been questioned based upon new machine learning research that shows that the AUC is quite noisy as a classification measure[17] and has some other significant problems in model comparison.[18][19] A reliable and valid AUC estimate can be interpreted as the probability that the classifier will assign a higher score to a randomly chosen positive example than to a randomly chosen negative example. However, the critical research[17][18] suggests frequent failures in obtaining reliable and valid AUC estimates. Thus, the practical value of the AUC measure has been called into question,[19] raising the possibility that the AUC may actually introduce more uncertainty into machine learning classification accuracy comparisons than resolution. Nonetheless, the coherence of AUC as a measure of aggregated classification performance has been vindicated, in terms of a uniform rate distribution,[20] and AUC has been linked to a number of other performance metrics such as the Brier score.[21]

One recent explanation of the problem with ROC AUC is that reducing the ROC Curve to a single number ignores the fact that it is about the tradeoffs between the different systems or performance points plotted and not the performance of an individual system, as well as ignoring the possibility of concavity repair, so that related alternative measures such as Informedness[6] or DeltaP are recommended.[22] These measures are essentially equivalent to the Gini for a single prediction point with DeltaP' = Informedness = 2AUC-1, whilst DeltaP = Markedness represents the dual (viz. predicting the prediction from the real class) and their geometric mean is the Matthews correlation coefficient.[6]

"
* https://www.r-bloggers.com/roc-curves-in-two-lines-of-r-code/
* http://blog.revolutionanalytics.com/2016/11/calculating-auc.html




HERMAN: say that I get going some more posts, especially on imbalanced distributions. and here I cover the "basics", there go into spesific case
