# ND111 - Intro to Machine Learning `Lesson03`

#### Tags
* Author : AH Uyekita
* Title  : _SVM_
* Date   : 14/01/2019
* Course : Data Science II - Foundations Nanodegree
    * COD    : ND111
    * **Instructor:** Katie Malone
    * **Instructor:** Sebastian Thrun

******************************************************************

## Support Vector Machine (SVM)

The Support Vector Machine was an algorithm invented by [Hava Siegelmann and Vladimir Vapnik][wikipedia_svm]. The objective of this algorithm is to fit a line to divide a group of point/features in two or more classes.

[wikipedia_svm]: https://en.wikipedia.org/wiki/Support-vector_machine

Figure 1 show the possibilities the line to segregate the two types of points.

<center><img src='01-img/c5_l3_01.png' alt='c5_l3_01.png' width="100%" />

<em>Figure 1 - .</em></center>

All the three lines could be a solution, but the SMV algorithm aims to minimize the sum of the square distance of each point to the line.
