---
layout: post
title: "Classification - Measuring Performance"
date: 2017-08-28
---

Hey there you beautiful ladies and gentlemen, señoras y señores, damen und herren, 女士们(們) 先生们(們 ! Hope everything is going well you.
In this post, I will write a bit about the how we measure the performance of classification models. We will concentrate on binary 
classification. We will look at the themes of

* Confusion Matrix
* Important ratios from the confusion matrix, and how the threshold impacts them and the volumes.
* Receiver operating characteristic (ROC), Area Under Curve, and other plots.



## Confusion Matrix
"Let us consider a two-class prediction problem (binary classification), in which the outcomes are labeled either as positive (p) or negative (n). There are four possible outcomes from a binary classifier. If the outcome from a prediction is p and the actual value is also p, then it is called a true positive (TP); however if the actual value is n then it is said to be a false positive (FP). Conversely, a true negative (TN) has occurred when both the prediction outcome and the actual value are n, and false negative (FN) is when the prediction outcome is n while the actual value is p.
" - https://en.wikipedia.org/wiki/Receiver_operating_characteristic


confusionMatrix(data = test_set$pred, reference = test_set$obs)



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
"
* https://www.r-bloggers.com/roc-curves-in-two-lines-of-r-code/
* http://blog.revolutionanalytics.com/2016/11/calculating-auc.html
