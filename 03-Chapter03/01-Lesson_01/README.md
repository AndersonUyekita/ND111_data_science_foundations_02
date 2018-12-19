# ND111 - Data Wrangling `Lesson01`

#### Tags
* Author : AH Uyekita
* Title  :  _Introduction to Data Wrangling_
* Date   : 18/12/2018
* Course : Data Science II - Foundations Nanodegree
    * COD    : ND111
    * **Instructor:** David Venturi
    * **Instructor:** Mat Leonard

#### Dataset

The dataset to this Chapter will be the [Online Job Post][armenia] from 2004 to 2015, it is hosted at [Kaggle][kaggle].

[armenia]: https://www.kaggle.com/udacity/armenian-online-job-postings
[kaggle]: https://www.kaggle.com

#### Softwares

The requirements for this lesson.

* [Anaconda][anaconda], and;
* [Jupyter Notebook][jupyter].

[anaconda]: https://anaconda.org/
[jupyter]: http://jupyter.org/

#### Tips

* <kbd>SHIFT</kbd> + <kbd>TAB</kbd>: Shows the function signature!!
* Anaconda prompt: jupyter notebook --notebook-dir='D:/'

#### Related Courses

* [UD170 - Introduction to Data Analysis][rel_1]

[rel_1]: https://br.udacity.com/course/intro-to-data-analysis--ud170

#### New functions/methods

`ASSERT`
```py
ASSERT 2 + 2 = 4
```
Do not show any error, but if FALSE shows a error.

`.rename()`
```py
df_clean.rename(columns={'ApplicationP': 'ApplicationProcedure',
                                    'AboutC': 'AboutCompany',
                                    'RequiredQual': 'RequiredQualifications',
                                    'JobRequirment': 'JobRequirements'})
```


********************************************************************************
## Introduction to Data Wrangling

There are roughly three steps in the Data Wrangling.

* Gathering;
* Assessing, and;
* Cleaning.

This is a iterate process between these three steps.

>Data wrangling is about gathering the right pieces of data, assessing your data's quality and structure, then modifying your data to make it clean. But the assessments you make and convert to cleaning operations won't make your analysis, viz, or model better, though. The goal is to just make them possible, i.e., functional.

>EDA is about exploring your data to later augment it to maximize the potential of our analyses, visualizations, and models. When exploring, simple visualizations are often used to summarize your data's main characteristics. From there you can do things like remove outliers and create new and more descriptive features from existing data, also known as feature engineering. Or detect and remove outliers so your model's fit is better.

>ETL: You also may have heard of the extract-transform-load process also known as ETL. ETL differs from data wrangling in three main ways:
>* The users are different
>* The data is different
>* The use cases are different
>This article (Data Wrangling Versus ETL: What’s the Difference?) by Wei Zhang explains these three differences well.

All text extracted from the class notes.

### Gathering

Gathering is the first step of a Data Wrangling, is also known as Collecting or Acquiring. The Armenian Online Job Post has 19,000 jobs postings from 2004 to 2015.

>Best Practice: Downloading Files Programmatically

This is the reasons:

* Scalability: This automation will save time, and prevents erros;
* Reproducibility: Key point to any research. Anyone could reproduce your work and check it.

### Assessing

The assessing in divided into two mains aspects:

* Quality of the dataset
* Tidiness of the dataset

#### Quality

Low quality dataset is related to a dirty dataset, which means the content quality of data.

Commom issues:

* Missing values
* Non standard units (km, meters, inches, etc. all mixed)
* Innacurate data, invalid data, inconsistent data, etc.

>One dataset may be high enough quality for one application but not for another.

#### Tidiness

Untidy data or _messy_ data, is about the structure of the dataset.

* Each obsevation by rows, and;
* Each variable/features by column.

This is the Hadley Wickham definition of tidy data.

### Assessing the data

There are two ways to assess the data.

* Visual, and;
* Programmatic.

#### Visual Assessment

Using regular tools, such as Graphics, Excel, tables, etc. It means, there is a human assessing the data.

#### Programmatic Assessment

Using automation to dataset evaluation is scalable, and allows you to handle a very huge quantity of data.

Examples of "Programmatic Assessment": Analysing the data using `.info()`, `.head()`, `.describe()`, plotting graphics (`.plot()`), etc..

Bear in mind, in this step we do not use "verbs" to describe any erros/problem, because the "verbs" will be actions to the next step.

### Cleaning

Improving the quality of a dataset or cleaning the dataset do not means: Changing the data (because it could be **data fraud**).

The meaning of Cleaning is correcting the data or removing the data.

* Innacurate, wrong or irrelevant data.
* Replacing or filling (NULL or NA values) data.
* Combining/Merging datasets.

Improving the tidiness is transform the dataset to follow:

* each observation = row
* each variable = column

There are two ways to cleaning the data: manually and programmatic.

#### Manually

To be avoided.

#### Programmatic

There are three steps:

1. Define
2. Code
3. Test

>**Defining** means defining a data cleaning plan in writing, where we turn our assessments into defined cleaning tasks. This plan will also serve as an instruction list so others (or us in the future) can look at our work and reproduce it.

>**Coding** means translating these definitions to code and executing that code.

>**Testing** means testing our dataset, often using code, to make sure our cleaning operations worked.

Text from the class notes.
