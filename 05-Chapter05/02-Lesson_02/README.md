# ND111 - Intro to Machine Learning `Lesson01`

#### Tags
* Author : AH Uyekita
* Title  : _Navie Bayes_
* Date   : 12/01/2019
* Course : Data Science II - Foundations Nanodegree
    * COD    : ND111
    * **Instructor:** Katie Malone
    * **Instructor:** Sebastian Thrun

******************************************************************

## Naive Bayes

Before dive in Naive Bayes. Let's talk a little bit about the thwo main groups in Machine Learning.

#### Supervised Learning {-}

>**In supervised learning, we are given a data set and already know what our correct output should look like**, having the idea that there is a relationship between the input and the output.
>
>Supervised learning problems are categorized into "regression" and "classification" problems. In a regression problem, we are trying to predict results within a continuous output, meaning that we are trying to map input variables to some continuous function. In a classification problem, we are instead trying to predict results in a discrete output. In other words, we are trying to map input variables into discrete categories.
>
>Example 1:
>
>Given data about the size of houses on the real estate market, try to predict their price. Price as a function of size is a continuous output, so this is a regression problem.
>
>We could turn this example into a classification problem by instead making our output about whether the house "sells for more or less than the asking price." Here we are classifying the houses based on price into two discrete categories.
>
>Example 2:
>
>- Regression - Given a picture of a person, we have to predict their age on the basis of the given picture
>
>- Classification - Given a patient with a tumor, we have to predict whether the tumor is malignant or benign. --- <cite>[Coursera Machine Learning Notebook][coursera_ml]</cite>

#### Unsupervised Learning {-}

>Unsupervised learning allows us to approach problems with little or no idea what our results should look like. We can derive structure from data where we don't necessarily know the effect of the variables.
>
>We can derive this structure by clustering the data based on relationships among the variables in the data.
>
>With unsupervised learning there is no feedback based on the prediction results.
>
>Example:
>
>Clustering: Take a collection of 1,000,000 different genes, and find a way to automatically group these genes into groups that are somehow similar or related by different variables, such as lifespan, location, roles, and so on.
>
>Non-clustering: The "Cocktail Party Algorithm", allows you to find structure in a chaotic environment. (i.e. identifying individual voices and music from a mesh of sounds at a cocktail party). --- <cite>[Coursera Machine Learning Notebook][coursera_ml]</cite>

[coursera_ml]: https://www.coursera.org/learn/machine-learning


### Gaussian - Naive Bayes

>In machine learning, naive Bayes classifiers are a family of simple "probabilistic classifiers" based on applying Bayes' theorem with strong (naive) independence assumptions between the features. --- <cite>[Wikipedia][wiki_url_naive_bayes]</cite>

[wiki_url_naive_bayes]: https://en.wikipedia.org/wiki/Naive_Bayes_classifier

The [Naive Bayes][bookdown_4.7] was one of the topics covered in Advanced Statistics.

[bookdown_4.7]: https://andersonuyekita.github.io/ND111_data_science_foundations_02/bayes-rule-lesson-07.html








### New Packages and Methods

In this lesson we are going to use the scikit learn package to perform the Gaussian Naive Bayes.

```py
from sklearn import svm
```

####




####
