# ND111 - Intro to Machine Learning `Lesson02`

#### Tags
* Author : AH Uyekita
* Title  : _Navie Bayes - Mini Project_
* Date   : 12/01/2019
* Course : Data Science II - Foundations Nanodegree
    * COD    : ND111
    * **Instructor:** Katie Malone
    * **Instructor:** Sebastian Thrun

#### Installing Python 2.7.15

I have also instaled the Python 2.7 in my desktop with Python 3.7.

[Step-by-step to set up the environments][medium_python27].

[medium_python27]: https://datascience.com.co/how-to-install-python-2-7-and-3-6-in-windows-10-add-python-path-281e7eae62a

******************************************************************

## Instructions

### Machine Learning for Author ID

A couple of years ago, J.K. Rowling (of Harry Potter fame) tried something interesting. She wrote a book, “The Cuckoo’s Calling,” under the name Robert Galbraith. The book received some good reviews, but no one paid much attention to it--until an anonymous tipster on Twitter said it was J.K. Rowling. The London Sunday Times enlisted two experts to compare the linguistic patterns of “Cuckoo” to Rowling’s “The Casual Vacancy,” as well as to books by several other authors. After the results of their analysis pointed strongly toward Rowling as the author, the Times directly asked the publisher if they were the same person, and the publisher confirmed. The book exploded in popularity overnight.

We’ll do something very similar in this project. We have a set of emails, half of which were written by one person and the other half by another person at the same company . Our objective is to classify the emails as written by one person or the other based only on the text of the email. We will start with Naive Bayes in this mini-project, and then expand in later projects to other algorithms.

We will start by giving you a list of strings. Each string is the text of an email, which has undergone some basic preprocessing; we will then provide the code to split the dataset into training and testing sets. (In the next lessons you’ll learn how to do this preprocessing and splitting yourself, but for now we’ll give the code to you).

One particular feature of Naive Bayes is that it’s a good algorithm for working with text classification. When dealing with text, it’s very common to treat each unique word as a feature, and since the typical person’s vocabulary is many thousands of words, this makes for a large number of features. The relative simplicity of the algorithm and the independent features assumption of Naive Bayes make it a strong performer for classifying texts. In this mini-project, you will download and install sklearn on your computer and use Naive Bayes to classify emails by author.
