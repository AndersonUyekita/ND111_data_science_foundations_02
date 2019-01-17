# ND111 - Intro to Machine Learning `Lesson05`

#### Tags
* Author : AH Uyekita
* Title  : _Choose your own algorithm_
* Date   : 16/01/2019
* Course : Data Science II - Foundations Nanodegree
    * COD    : ND111
    * **Instructor:** Katie Malone
    * **Instructor:** Sebastian Thrun

******************************************************************

## Choose your own algorithm

In this lesson I have to choose one of three listed algorithm to apply it by myself without any "instructions".

Algorithm:

* K nearest neighbors: Classic, simple, easy to understand;
* AdaBoost
* Random Forest

The last two, Adaboost and Random Forest, are the so-called "ensemble methods". Meta classifiers built from (usually) decision trees.

#### Ensemble Methods {-}

>The goal of ensemble methods is to combine the predictions of several base estimators built with a given learning algorithm in order to improve generalizability / robustness over a single estimator.
>
>Two families of ensemble methods are usually distinguished:
>
>In averaging methods, the driving principle is to build several estimators independently and then to average their predictions. On average, the combined estimator is usually better than any of the single base estimator because its variance is reduced.
>
>Examples: Bagging methods, Forests of randomized trees, …
>
>By contrast, in boosting methods, base estimators are built sequentially and one tries to reduce the bias of the combined estimator. The motivation is to combine several weak models to produce a powerful ensemble.
>
>Examples: AdaBoost, Gradient Tree Boosting, … --- <cite>[Scikit Learn][sk_learn_ensemble]</cite>

[sk_learn_ensemble]: https://scikit-learn.org/stable/modules/ensemble.html

### Investigation Process

1. Do some research to get a general understanding.
2. Scikit Learn Documentation
3. Hands on
4. Make predictions
5. Evaluate the accuracy

### K Nearest neighbors (KNN)

From Wikipedia:

>In pattern recognition, the k-nearest neighbors algorithm (k-NN) is a non-parametric method used for classification and regression.[1] In both cases, the input consists of the k closest training examples in the feature space. The output depends on whether k-NN is used for classification or regression:
>* In k-NN classification, the output is a class membership. An object is classified by a plurality vote of its neighbors, with the object being assigned to the class most common among its k nearest neighbors (k is a positive integer, typically small). If k = 1, then the object is simply assigned to the class of that single nearest neighbor.
>* In k-NN regression, the output is the property value for the object. This value is the average of the values of its k nearest neighbors. --- <cite>[Wikipedia][wiki_knn]</cite>

[wiki_knn]: https://en.wikipedia.org/wiki/K-nearest_neighbors_algorithm

#### `KNeighborsClassifier` {-}

This is a part of the Scikit Learn package and you can use the `KNeighborsClassifier` classifier.

```py
# Importing the K Nearest Neighbors from Scikit learn package.
from sklearn.neighbors import KNeighborsClassifier

# Creating the classifier.
clf = KNeighborsClassifier(n_neighbors=5)

# Training or fitting the model.
clf.fit(features_train, labels_train)

# Predicting
pred = clf.predict(features_test)
```

### Adaboost

Also from Wikipedia:

>AdaBoost, short for Adaptive Boosting, is a machine learning meta-algorithm formulated by Yoav Freund and Robert Schapire, who won the 2003 Gödel Prize for their work. It can be used in conjunction with many other types of learning algorithms to improve performance. The output of the other learning algorithms ('weak learners') is combined into a weighted sum that represents the final output of the boosted classifier. AdaBoost is adaptive in the sense that subsequent weak learners are tweaked in favor of those instances misclassified by previous classifiers. AdaBoost is sensitive to noisy data and outliers. In some problems it can be less susceptible to the overfitting problem than other learning algorithms. The individual learners can be weak, but as long as the performance of each one is slightly better than random guessing, the final model can be proven to converge to a strong learner.
>Every learning algorithm tends to suit some problem types better than others, and typically has many different parameters and configurations to adjust before it achieves optimal performance on a dataset, AdaBoost (with decision trees as the weak learners) is often referred to as the best out-of-the-box classifier.[1][2] When used with decision tree learning, information gathered at each stage of the AdaBoost algorithm about the relative 'hardness' of each training sample is fed into the tree growing algorithm such that later trees tend to focus on harder-to-classify examples. --- <cite>[Wikipedia][wiki_adaboost]</cite>

[wiki_adaboost]: https://en.wikipedia.org/wiki/AdaBoost

From Scikit Learn:

>The module sklearn.ensemble includes the popular boosting algorithm AdaBoost, introduced in 1995 by Freund and Schapire [FS1995].
>
>The core principle of AdaBoost is to fit a sequence of weak learners (i.e., models that are only slightly better than random guessing, such as small decision trees) on repeatedly modified versions of the data. The predictions from all of them are then combined through a weighted majority vote (or sum) to produce the final prediction. The data modifications at each so-called boosting iteration consist of applying weights , , …,  to each of the training samples. Initially, those weights are all set to , so that the first step simply trains a weak learner on the original data. For each successive iteration, the sample weights are individually modified and the learning algorithm is reapplied to the reweighted data. At a given step, those training examples that were incorrectly predicted by the boosted model induced at the previous step have their weights increased, whereas the weights are decreased for those that were predicted correctly. As iterations proceed, examples that are difficult to predict receive ever-increasing influence. Each subsequent weak learner is thereby forced to concentrate on the examples that are missed by the previous ones in the sequence [HTF]. --- <cite>[Scikit Learn][sk_learn_adaboost]</cite>

[sk_learn_adaboost]: https://scikit-learn.org/stable/modules/ensemble.html#adaboost

#### `AdaBoostClassifier` {-}

This is a part of the Scikit Learn package and you can use the `AdaBoostClassifier` classifier.

```py
# Importing the AdaBoost from Scikit learn package.
from sklearn.ensemble import AdaBoostClassifier

# Creating the classifier.
clf = AdaBoostClassifier()

# Training or fitting the model.
clf.fit(features_train, labels_train)

# Predicting
pred = clf.predict(features_test)
```



### Random Forest

>Random forests or random decision forests are an ensemble learning method for classification, regression and other tasks that operates by constructing a multitude of decision trees at training time and outputting the class that is the mode of the classes (classification) or mean prediction (regression) of the individual trees.[1][2] Random decision forests correct for decision trees' habit of overfitting to their training set.[3]:587–588
>The first algorithm for random decision forests was created by Tin Kam Ho[1] using the random subspace method,[2] which, in Ho's formulation, is a way to implement the "stochastic discrimination" approach to classification proposed by Eugene Kleinberg. --- <cite>[Wikipedia][wiki_random]</cite>

[wiki_random]: https://en.wikipedia.org/wiki/Random_forest


#### `RandomForestClassifier` {-}

This is a part of the Scikit Learn package and you can use the `RandomForestClassifier` classifier.

```py
# Importing the Random Forest from Scikit learn package.
from sklearn.ensemble import RandomForestClassifier

# Creating the classifier.
clf = RandomForestClassifier()

# Training or fitting the model.
clf.fit(features_train, labels_train)

# Predicting
pred = clf.predict(features_test)
