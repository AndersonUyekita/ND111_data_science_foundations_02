# ND111 - Advanced Statistics `Lesson09`

#### Tags
* Author : AH Uyekita
* Title  : _Normal Distribution Theory_
* Date   : 06/01/2019
* Course : Data Science II - Foundations Nanodegree
    * COD    : ND111
    * **Instructor:** Sebastian Thrun
    * **Instructor:** Josh Bernhard

********************************************************************************

## Normal Distribution Theory

Comparison between a simple probability, binomial distribution, and normal distribution.

|Type|Quantity|
|:-:|:-:|
|Bernoulli|1|
|Binomial|10|
|Normal|1000|

Along this chapter I have seen the evolution from the simple probability (Bernoulli), to a Binomial, and finally a Normal distribution.

The difference is the size of the "sample".

### Equations

* Bernoulli

$$ P(HEADS) = P(HEADS)^n \tag{1}$$

* Binomial

$$P(n,k) = \frac{n!}{(n-k)!k!} p^k * (1-p)^{n-k} \tag{2}$$

* Normal (or Gaussian or Gauss or Laplace–Gauss) distribution

$$N(x;\mu,\sigma^2) = \frac{1}{\sqrt{2\pi\sigma^2}}\exp^{-\frac{1}{2} \frac{(x-\mu)^2}{\sigma^2}} \tag{3}$$

$\mu$: mean;
$\sigma^2$: variance.
