Here I list some topics of upcoming posts:

* OBS: these guys have a lot of nice content, but very tricky to get and read: https://www.analyticsvidhya.com/blog/2016/03/practical-guide-deal-imbalanced-classification-problems/
So make it more fun and easy. And much shorter. Can instead make it in many parts

* Intro to ML in R - Caret - [Intro xgboost](https://xgboost.readthedocs.io/en/latest/model.html)
* How to measure your ML-model 
https://topepo.github.io/caret/measuring-performance.html
Imbalanced: http://journals.plos.org/plosone/article?id=10.1371/journal.pone.0118432
https://topepo.github.io/caret/model-training-and-tuning.html#metrics
http://blog.revolutionanalytics.com/2016/11/calculating-auc.html how to calculate AUC. Må skjønne dette skikkelig
Imbalanced : https://www.analyticsvidhya.com/blog/2016/03/practical-guide-deal-imbalanced-classification-problems/
Tutorial xgboost : https://xgboost.readthedocs.io/en/latest/model.html
https://github.com/dmlc/xgboost/blob/master/doc/parameter.md

* this is awesome: https://jobs.zalando.com/tech/blog/what-is-hardcore-data-science--in-practice/?gh_src=4n3gxh1

* How to select hyperparams?
https://cran.r-project.org/web/packages/rBayesianOptimization/rBayesianOptimization.pdf
http://blog.revolutionanalytics.com/2016/06/bayesian-optimization-of-machine-learning-models.html
https://www.r-bloggers.com/simulated-annealing-feature-selection/
https://cran.r-project.org/web/packages/GenSA/GenSA.pdf

* business of AI HBR: https://hbr.org/cover-story/2017/07/the-business-of-artificial-intelligence

* Tree models
What is desicion trees, bagging, boosting, random forrest? A very good book to understand the ML-techniques: Intro to statistical learning. See also my emails etc if I find those nice videoes..

* Lean analytics

* Full stack data science/ mining : http://myweb.sabanciuniv.edu/rdehkharghani/files/2016/02/The-Morgan-Kaufmann-Series-in-Data-Management-Systems-Jiawei-Han-Micheline-Kamber-Jian-Pei-Data-Mining.-Concepts-and-Techniques-3rd-Edition-Morgan-Kaufmann-2011.pdf

* Some more intro to the concept of data science
https://www.coursera.org/learn/data-science-course

* Spark/Scala/Hadoop --> courses
https://www.coursera.org/learn/scala-spark-big-data
https://www.udemy.com/scala-and-spark-for-big-data-and-machine-learning/?utm_source=adwords-learn&utm_medium=udemyads&utm_campaign=NEW-AW-PROS-PROF-ROW-DSA-EN-EURO_._ci__._sl_ENG_._vi_PROF_._sd_All_._la_EN_._&utm_content=deal4584&utm_term=_._ag_43090399814_._ad_205975711605_._de_c_._dm__._pl__._ti_dsa-334302743689_._li_1010826_._pd__._&gclid=CjwKCAjwrO_MBRBxEiwAYJnDLFydAnKQXqsOyjd9TgnRde7B_X_XzqhVrYfRyWRvq98aE51iSMRamhoCHukQAvD_BwE
https://mapr.com/blog/apache-spark-vs-mapreduce-whiteboard-walkthrough/

* Applications
Hedge funds very nice : https://www.ft.com/content/d86ad460-8802-11e7-bf50-e1c239b45787
FS in general: http://www.kdnuggets.com/2017/09/machine-learning-algorithms-lending.html#%2EWbl2aYGefhw%2Elinkedin





Cross validation: 
- Man tar et "test set" av treningssettet, og validerer på dette settet etter har lagd en model. Gjør dette flere ganger har vi k-fold, der vi setter opp k bins. Vi velger så den modellen som ga lavest error. SÅ tankegangen er "litt" som bagging,, for fortsatt helt forskjellig konsept. https://www.youtube.com/watch?v=sFO2ff-gTh0. : https://www.youtube.com/watch?v=TIgfjmp-4BA


Bagging (bootstrap aggregating)
- tar ut et subset n av treninsettet tilfeldig med replacement, og lager en modell. Gjør dette m ganger (m bags). Så tar average modell og bruker. Gjør ingen cross validation som default (men kan sikkert adde på som på boosting). https://www.youtube.com/watch?v=2Mg8QD0F1dQ

Random Forest:
- Tar bagging, men tar et utvalg av predictors hver gang! https://www.youtube.com/watch?v=6yICuCnlh5Q



Boosting:
- ganske likt bagging; men tar ikke bare average. For hver bag du lager, legger du mer vekt på det du predikterte dårlig, i neste bag! Så boosting så gror du treet SEKVELSIELT, altså ikke som med bagging og RF som gjør det parallelt.... Gjør en test på treningssettet, så det er litt nærmere  bagging + cross validation. Men ikke helt samme tankegangen, fordi bla boosting vektlegger på en spesiell måte (som gradient boosting feks). https://www.youtube.com/watch?v=GM3CDQfQ4sw

