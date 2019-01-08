# ND111 - Advanced Statistics `Lesson11`

#### Tags
* Author : AH Uyekita
* Title  : _Confidence Intervals_
* Date   : 07/01/2019
* Course : Data Science II - Foundations Nanodegree
    * COD    : ND111
    * **Instructor:** Sebastian Thrun
    * **Instructor:** Josh Bernhard

********************************************************************************

## Confidence Intervals

Have in mind this is a part of Inference Statistical.

In this lesson we are going to use the sampling method to create our interval of confidence. The steps is very simple:

* From a population gather a sample;
* Based on this sample draw many new samples (e.g. 10,000);
    * The size of these 10,000 samples should be "large" (e.g. 200);
    * You can use the `replace = True` to work with Bootstrapping;
* Calculate some statistics (of this 200 elements): mean or difference of means;
* Plot a histogram of this statistics (should have 10,000 elements to plot).

Plotting this histogram you can take some conclusions about the data. For example:

- If you decided to use difference of means, you can check if the two "samples" are equals, or greater or less than.

>Assuming you control all other items of your analysis:

>1. Increasing your sample size will decrease the width of your 2. confidence interval.
>2. Increasing your confidence level (say 95% to 99%) will increase the width of your confidence interval.

>You saw that you can compute:

>1. The confidence interval **width** (Confidence Interval Width) as the difference between your upper and lower bounds of your confidence interval.
>2. The **margin of error** (MOE) is half the confidence interval width, and the value that you add and subtract from your sample estimate to achieve your confidence interval final results. --- <cite>Udacity class notes</cite>

### Practical and Statistical Significance

* Confidence Intervals will provide a Statistical Significance to be used as bedrock of a conclusion.
* Practical Significance is something from outside of the Confidence Interval and could decide if this solution is good or not. The Practical Significance takes account other variables (costs, lack of employee, time, etc.).

### Traditional Methods vs Bootstrapping Confidence Intervals

The Bootstrapping Methods can perform all traditional methods of Confidence Intervals with minors differences when the sample is a true representation of the population.

>With large sample sizes, these end up looking very similar. With smaller sample sizes, using a traditional methods likely has assumptions that are not true of your interval. Small sample sizes are not ideal for bootstrapping methods though either, as they can lead to misleading results simply due to not accurately representing your entire population well.

Traditional Methods of Confidence Intervals:

* T-Test: Population mean;
* Two sample T-test: Comparing two means;
* Z-Test;
* Chi-squared test;
* F-test.

### Misinterpretation of Confidence Intervals

The aim of a Confidence Interval is to calculate parameter, a single value of a entire population, which could be:

* mean
* standard deviation
* difference between two means (two populations means)
* Any other numeric summary in the population

Confidence Interval **do not** allow us to tell about any specific individual of this population.

>Confidence intervals take an aggregate approach towards the conclusions made based on data, as these tests are aimed at understanding population parameters (which are aggregate population values).

>Alternatively, machine learning techniques take an individual approach towards making conclusions, as they attempt to predict an outcome for each specific data point.

>In the final lessons of this class, you will learn about two of the most fundamental machine learning approaches used in practice: linear and logistic regression. --- <cite>Udacity Class notes</cite>

### New Methods

#### `.sample()`

Will sample a data frame, you can use `replace = True` if you are wondering perform a bootstrap.

```{py}
my_population.sample(100, replace = True)
```
For above example the sample size is 100 and there is replacement (which denotes it is a boootstrapping process).

#### `.percentile()`

This is a numpy method, and gives the percentile from a given value.

```{py}
np.percentile(df, 0.5), np.percentile(df, 99.5)
```

There are two `.percentile()` representing a two tailed confidence interval of 99%.
