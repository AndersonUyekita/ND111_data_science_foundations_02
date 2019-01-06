# ND111 - Advanced Statistics `Lesson05`

#### Tags
* Author : AH Uyekita
* Title  : _Binomial Distribution_
* Date   : 05/01/2019
* Course : Data Science II - Foundations Nanodegree
    * COD    : ND111
    * **Instructor:** Sebastian Thrun
    * **Instructor:** Josh Bernhard

********************************************************************************

## Binomial Distribution

>In probability theory and statistics, the binomial distribution with parameters n and p is the discrete probability distribution of the number of successes in a sequence of n independent experiments, each asking a yes–no question, and each with its own boolean-valued outcome: a random variable containing a single bit of information: success/yes/true/one (with probability p) or failure/no/false/zero (with probability q = 1 − p). A single success/failure experiment is also called a Bernoulli trial or Bernoulli experiment and a sequence of outcomes is called a Bernoulli process; for a single trial, i.e., n = 1, the binomial distribution is a Bernoulli distribution. The binomial distribution is the basis for the popular binomial test of statistical significance. <cite>[Wikipedia][wiki_bin_dis]</cite>

[wiki_bin_dis]: https://en.wikipedia.org/wiki/Binomial_distribution

**Example 1:** 5 coin flips. $P(\text{two HEADS})$.

* The order of the HEADS do not matter.

What's the number of combinations?

|Flip 1|Flip 2|Flip 3|Flip 4|Flip 5|
|:-:|:-:|:-:|:-:|:-:|
|H|?|?|?|?|
|H|H|?|?|?|
|5|4|1|1|1|

You can place H in 5 places, after place the first H you only have 4 places. For this reason, there are 20 posibilities.

$$ P_1 = 5 * 4 = 20 $$

Bear in mind, the H's are equal and you can swap each one.

|$H_1$|$H_2$|
|:-:|:-:|
|?|?|
|2|1|

So there are two possible H's to insert in the $H_1$

$$ P_2 = 2 * 1 = 2 $$

What this $P_2$ means?

> You have two equals instances so the $P_1$ has double entries. The good part is the $P_2$ is used to "fix" it.

$$ P = \frac{P_1}{P_2} = \frac{20}{2} = 10 $$

**Example 2:** 10 coin flips. $P(\text{four HEADS})$.

* The order of the HEADS do not matter.

What's the number of combinations?

|Flip 1|Flip 2|Flip 3|Flip 4|Flip 5|Flip 6|Flip 7|Flip 8|Flip 9|Flip 10|
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|H|?|?|?|?|?|?|?|?|?|
|H|H|H|T|H|T|T|T|T|T|
|10|9|8|1|7|1|1|1|1|1|

You can place H in 10 places, after place the first H you only have 9 places. For this reason, there are ($10*9*8*7$) posibilities.

$$ P_1 = 10*9*8*7 = 5,040 $$

Bear in mind, the H's are equal and you can swap each one.

|$H_1$|$H_2$|$H_3$|$H_4$|
|:-:|:-:|:-:|:-:|
|?|?|?|?|
|4|3|2|1|

So there are two possible H's to insert in the $H_1$

$$ P_2 = 4 * 3 * 2 * 1 = 24 $$

What this $P_2$ means?

> You have two or more equals instances so the $P_1$ has "double" entries. The good part is the $P_2$ is used to "fix" it.

$$ P = \frac{P_1}{P_2} = \frac{5,040}{24} = 210 $$

### Equation

Founded on the examples above, it is possible to write a equation, given 10 flips ($k$) and an expected 3 heads ($n$).

$$ P = \frac{P_1}{P_2} = \frac{10 * 9 * 8}{\underbrace{3 * 2 * 1}_{3!}}$$

Let's multiply by ($7 * 6 * 5 * 4 * 3 * 2 * 1$) or simply by $7!$.

$$ P = \frac{P_1}{P_2} = \frac{10 * 9 * 8 * 7!}{3! * 7!} = \frac{\overbrace{10!}^{k!}}{\underbrace{3!}_{n!} * \underbrace{7!}_{(k-n)!}} = \frac{k!}{n!(k-n)!} \tag{1}$$

Equation (1) is also noted as:

$$ C_{n,k} = \begin{pmatrix} n \\ k \end{pmatrix} \tag{2}$$

Equation (2) will only calculate the number of combinations. We can aggregate the probability.

* $P(H)$: for heads;
* $P(T)$: for tails;

Given the 10 coins flips, the probability for a single instance, no matter the order:

_Obs.: Do not confound with permutation notation._

$$ P_{k,n} = P(H)^n * P(T)^{k-n}$$
$$ P_{10,3} = P(H)^3 * P(T)^{7}\tag{3}$$

For a fair coin.

$$ P_{10,3} = 0.5^3 * 0.5^{7} = 0.000976563 \tag{4}$$

The value of $P(10,3)$ is for a single time, I know there are many instances where could happen 3 heads, for this reason I use the combination.

$$ C_{10,3} = \begin{pmatrix} 10 \\ 3 \end{pmatrix} = \frac{10!}{7!*3!} = 120$$

The probability to happen 3 heads in 10 flips coins is:

$$ P(10|3) = C_{10,3} * P_{10,3} = 120 * 0.000976563 = 0.1171875 $$

Expanding this concept to a all around equation:

$$ P(k|n) = \underbrace{C_{k,n}}_{\text{note 1}} * \underbrace{P_{k,n}}_{\text{note 2}} \tag{5}$$

* note 1: Probability to occur the given _combination_ (3 heads and 7 tails) over the all combinations ($10^2 = 1,024$);
* note 2: Probability based on the coins (heads and tails probabilities).

#### Additional Info

Do not confound Permutation with Combination.

* Combination: When the order does not matter;
* Permutation: When the order is important.

Read more in [mathplanet][binomial_source].

[binomial_source]: https://www.mathplanet.com/education/algebra-2/discrete-mathematics-and-probability/permutations-and-combinations
