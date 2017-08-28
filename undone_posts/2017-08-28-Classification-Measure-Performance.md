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
