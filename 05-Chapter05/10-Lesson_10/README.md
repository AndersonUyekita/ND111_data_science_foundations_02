# ND111 - Intro to Machine Learning `Lesson10`

#### Tags
* Author : AH Uyekita
* Title  : _Features Scaling_
* Date   : 21/01/2019
* Course : Data Science II - Foundations Nanodegree
    * COD    : ND111
    * **Instructor:** Katie Malone
    * **Instructor:** Sebastian Thrun

******************************************************************

## Features Scaling

This is a method to scaling the range of the features of a data set, there are some ways to do it, and in this lesson we will cover the simplest one, which use the maximum and minimum values.

>Feature scaling is a method used to standardize the range of independent variables or features of data. In data processing, it is also known as data normalization and is generally performed during the data preprocessing step. --- <cite>[Wikipedia][wiki_feature_scaling]</cite>

[wiki_feature_scaling]: https://en.wikipedia.org/wiki/Feature_scaling

### Feature Scaling Formula

In this lesson we will use equation (1) to scaling:

$$x' = \frac{x - min}{max - min} \tag{1}$$

Where:

* $x':$ the value of $x$ scaled;
* $x:$ the value we want to scale;
* $max:$ the maximum value of all x's values, and;
* $min:$ the minimum value of all x's values.

Now, the output from $x$ varies from [0, 1], the beneficit of this action is to minimize the dominance of some variable against other.

### Scaling in Scikit Learn

The Scikit Learn also has the scaling functions, it is called preprocessing data.

```py
# Loading the Scaling package from the Scikit Learn.
from sklearn import preprocessing
```

The Scikit Learn Package has several way to Preprocessing and Normalization, you can see the complete list [here][scikit_learn_preprocessing_list].

[scikit_learn_preprocessing_list]: https://scikit-learn.org/stable/modules/classes.html#module-sklearn.preprocessing

The one we will use in this lesson is the `MinMaxScaler`.

#### Scaling features to a range {-}

>An alternative standardization is scaling features to lie between a given minimum and maximum value, often between zero and one, or so that the maximum absolute value of each feature is scaled to unit size. This can be achieved using MinMaxScaler or MaxAbsScaler, respectively. --- <citer>[Scikit Learn][scikit_learn_scaling]</cite>

[scikit_learn_scaling]: https://scikit-learn.org/stable/modules/preprocessing.html#scaling-features-to-a-range

The steps to use this scaling is almost the same comparing to the regression, SVM, DT, etc. First, create a classifier, later fit it (and transform).


#### `.MinMaxScaler()` {-}

This is a step-by-step of how to scale.

```py
# Importing the MinMaxScaler from the preprocessing.
from sklearn.preprocessing import MinMaxScaler

# Creating a classifier.
min_max_scaler = MinMaxScaler()

# Fitting: This methods calcs the min and max.
min_max_scaler.fit(X)

# This is what we are looking for the scaled X.
X_scaled = min_max_scaler.transform(X)
```

Where:

* $X$: Is the features to be scaled.

There are a method which simplify performing the fit and transform in a single step.

```py
# This is the same of using .fit() and later .transform()
X_scaled = min_max_scaler.fit_transform(X)
```

### Affected Algorithms

The SVM and K-Means are directed affected by the scaling process, because these two algorithms uses the trade-off between features to adjust the fitness.


.
