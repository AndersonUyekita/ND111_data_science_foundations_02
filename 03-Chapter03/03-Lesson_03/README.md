# ND111 - Data Wrangling `Lesson03`

#### Tags
* Author : AH Uyekita
* Title  :  _Assessing Data_
* Date   : 25/12/2018
* Course : Data Science II - Foundations Nanodegree
    * COD    : ND111
    * **Instructor:** David Venturi
    * **Instructor:** Mat Leonard

#### Related Courses

* [UD595 - Get Into the Shell][rel_1]
* [UD001 - Intro to HTML and CSS][rel_2]

[rel_1]: https://classroom.udacity.com/courses/ud595

#### Dataset

This lesson use a fictional dataset of insulin drugs.

>The Auralin and Novodra are **not** real insulin products. This clinical trial data was fabricated for the sake of this course. When assessing this data, the issues that you'll detect (and later clean) are meant to simulate real-world data quality and tidiness issues.


********************************************************************************

## Assessing Data

This is the second step of the Data Wrangling, and the aims of this lesson is to explain some details. There are two kind of _unclean_ data:

* Quality issues: Dirty data;
    * Missing, duplicated, or incorrect data;
* Lack of tidiness: Also known as messy data.
    * Strucutural issues

There are two ways to assess:

* Visual: Plotting a simple graphic or visualizing the table (rows and columns);
* Programmatic: Using code to summarize the data frame using .info(), .describe(), average, summation, max, min, etc..

#### Dirty Data

Is related to the content issues, as known as low quality data.

* Innacurated data: Typos, corrupted, and duplicated data;

#### Messy Data

Messy data is related to structural issues, as known as untidy data.

* Each observation is a row;
* Each variable/features is a column;
* Based on the Hadley Wickham principles of tidy data.

### Assess Proccess

In both cases (visual or programmatic), we could be divided into two main steps:

* Detect;
* Document.

### Data Quality Dimensions

>Data quality dimensions help guide your thought process while assessing and also cleaning. The four main data quality dimensions are:

* Completeness: Missing values;
* Validity: Invalid value (like negative height or weight, zip code with only 4 digits, etc.);
* Accuracy: Wrong data which is valid (like the typo in the height);
* Consistency: Data without a standard notation (New York and NY, Colorado and CO, same information but differents notations).

The severity of this problem is decreasing order: Completeness, Validity, Accuracy, and Consistency.
