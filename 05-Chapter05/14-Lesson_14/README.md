# ND111 - Intro to Machine Learning `Lesson14`

#### Tags
* Author : AH Uyekita
* Title  : _Validation_
* Date   : 24/01/2019
* Course : Data Science II - Foundations Nanodegree
    * COD    : ND111
    * **Instructor:** Katie Malone
    * **Instructor:** Sebastian Thrun

******************************************************************

## Cross Validation

The principle of Cross-validation is to divide the dataset into  training dataset and test dataset. This is very useful to evaluate the model, because you will use an independet and real data to assess it.

Have in mind, when you use the entire dataset to train your model you will fall in overfitting.

Even more, Cross validation go further is not only splitting the data into training and test datasets, it uses a concept of rotation, which will run several times (iterations) the same model, but changing the content of training and test datasets.

This is performed using the concept called folds, it is a straightforward way to divide the dataset into several blocks of information, each fold will be use once per time as the testing dataset. Figure 1 shows an example of it.

<center><img src="01-img/c5_l14_01.jpg" alt="Cross Validation and Folds" width="80%;"/>

<em>Figure 1 - Folds of the Dataset.</em></center>

For each iteration the test data was changed and also the training data. The result is the average of the accuracy from all iterations.

The Scikit Learn package has the modual model_selectio, which has the Cross validation concept.

### Model Selection

This is the module use in the whole chapter to divide the dataset into training and testing.

```py
# This module split the data set automatically.
from sklearn.model_selection import train_test_split
```

#### `.train_test_split` {-}

This function will returns 4 datasets.

* Features
    * Training
    * Testing
* Labels
    * Training
    * Testing
```py
# 10% od all dataset will be used as test.
features_train, features_test, labels_train, labels_test = train_test_split(features, labels, test_size = 0.1, random_state = 42)
```
Where:

* test_size: Size of the test dataset in percentage of the total;
* random_state: Random seed to turn it reproducible.

#### `.KFold()`

The `.KFold()` will create an object to be used in using `.get_n_splits()` and `.split()` methods. Read more in Scikit Learn [Website][scikit_learn_kfold].

```py
# Importing the KFold.
from sklearn.model_selection import KFold
```

An example of how to use it.

```py
# Creates the object of K-fold.
kf = KFold(n_splits = 2)

# Return a iterator.
kf.get_n_splits(X)

# Split the iterator to generate the index.
# Will create 4 datasets.
for train_index, test_index in kf.split(X):
   X_train, X_test = X[train_index], X[test_index]
   y_train, y_test = y[train_index], y[test_index]
```
As you can see you need to use a `.for()` loop to use the `.KFold`.

[scikit_learn_kfold]: https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.KFold.html#sklearn.model_selection.KFold

#### `.GridSearchCV()` {-}

The `.GridSearchCV()` aims to automate the simulations varying the coefficients. You can create a dictionary of parameters with all values to be simulated (all combinations).

```py
# Importing SVM
from sklearn import svm

# importing the GridSearchCV
from sklearn.model_selection import GridSearchCV

# Parameters I want to varyself.
parameters = {'kernel':('linear', 'rbf'), 'C':[1, 10]}

# Creating a classifier of SMV (I choose this algorithm as example).
svc = svm.SVC(gamma="scale")

# Creating the object of my GridSearchCVself.
clf = GridSearchCV(svc, parameters, cv=5)

# Fitting/Trainning my object.
clf.fit(X_train, Y_test)
```
