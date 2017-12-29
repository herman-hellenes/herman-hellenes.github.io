---
layout: post
title: "Classification - Measuring Performance"
date: 2017-08-28
comments: true
---

Hey there ! Hope everything is going well you.

How do you measure how good your model is? This might seem like a simple question, however it is quite intricate. This is one of the most important thing to get right doing Data Science. As in all other sciences, running experiments and measuring the results in an unbiased way, is really the core of it all. For those of you having a background in science, you sure know how much effort is put into these steps in the lab. It is the same thing here!

In this post, we will look into measuring the performance of classification models. Binary 
classification models to be precise. Such models are rather intuitive, as well as they are very suited to problems you will face in both business and academia. We will look at the themes of

* Confusion Matrix
* Important ratios from the confusion matrix, and how the threshold impacts them and the volumes.
* Receiver operating characteristic (ROC), Area Under Curve, and other plots.



## Confusion Matrix
First of all, a binary classification problem is simply to lable each of your situations into two classes. As a practical example, say you are working for an insurance firm. You observe that the churn is high on a certain product, without there being some very obious reason for this. Given that you have access to relevant data of your customer, you can construct a model that predicts if the current costumers will leave your firm, or not. This should then be used to do some action; for instance to call up the clients with a high chance of leaving and offer them a lower price. Note: in this situation it is useful to account for the expected return from the customer as well as numerous other details, but that is another story.

<p align="center">
  <img width="400" height="200" src="/figs/classification_measure/validation_ml.png">
</p>


Here we have a binary classification problem, where the labels are "churn" or "no churn". The convension is to rather say "positive" (p) or "negative" (n), in order to be more general. So say you have build a model you would like to evaluate. We take a unseen test set of customers, meaning the model has not seen this data before, but we sit with the correct lables to verify how well the model perform. When applying the model on the current customers, we have four possible outcomes per customer:
* The correct lable is positive and the model predicted positive. This is called true positive (TP).
* The correct lable is negative and the model predicted positive. This is called false positive (FP).
* The correct lable is positive and the model predicted negative. This is called false negative (FN).
* The correct lable is negative and the model predicted negative. This is called true negative (TN).

So, say we try to test the model with 100 positive observation, and 100 negative observations. In total 200 persons like George in the figure above. Now things are becoming interesting, since we will need a lot of observations to find anything statistical significant about our model performance. Let's consider the following result

<p align="center">
  <img width="300" height="200" src="/figs/classification_measure/conf_matrix_1.png">
</p>






confusionMatrix(data = test_set$pred, reference = test_set$obs)

sensitivity, recall, hit rate, or true positive rate (TPR)
{\displaystyle \mathrm {TPR} ={\frac {\mathrm {TP} }{P}}={\frac {\mathrm {TP} }{\mathrm {TP} +\mathrm {FN} }}} {\displaystyle \mathrm {TPR} ={\frac {\mathrm {TP} }{P}}={\frac {\mathrm {TP} }{\mathrm {TP} +\mathrm {FN} }}}
specificity or true negative rate (TNR)
{\displaystyle \mathrm {TNR} ={\frac {\mathrm {TN} }{N}}={\frac {\mathrm {TN} }{\mathrm {TN} +\mathrm {FP} }}} {\displaystyle \mathrm {TNR} ={\frac {\mathrm {TN} }{N}}={\frac {\mathrm {TN} }{\mathrm {TN} +\mathrm {FP} }}}
precision or positive predictive value (PPV)
{\displaystyle \mathrm {PPV} ={\frac {\mathrm {TP} }{\mathrm {TP} +\mathrm {FP} }}} {\displaystyle \mathrm {PPV} ={\frac {\mathrm {TP} }{\mathrm {TP} +\mathrm {FP} }}}
negative predictive value (NPV)
{\displaystyle \mathrm {NPV} ={\frac {\mathrm {TN} }{\mathrm {TN} +\mathrm {FN} }}} {\displaystyle \mathrm {NPV} ={\frac {\mathrm {TN} }{\mathrm {TN} +\mathrm {FN} }}}


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
