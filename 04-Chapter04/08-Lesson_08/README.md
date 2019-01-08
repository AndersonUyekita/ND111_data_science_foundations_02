# ND111 - Advanced Statistics `Lesson08`

#### Tags
* Author : AH Uyekita
* Title  : _Python Probability Practice_
* Date   : 06/01/2019
* Course : Data Science II - Foundations Nanodegree
    * COD    : ND111
    * **Instructor:** Sebastian Thrun
    * **Instructor:** Josh Bernhard

********************************************************************************

## Python Probability Practice

Some methods interesting to take notes.

#### `.random.randint()`

Generates a random value.
```r
np.random.randint(0, 2, size=10000)
```
In the example above, the line code will generate a sample of 10,000 number from 0 to 1 (the 2 is not inclusive).

#### `.random.choice()`

Generates a radom value with different loads.

```r
np.random.choice([0, 1], size=10000, p=[0.8, 0.2]))
```

In the example the loads are 0.8 and 0.2.

#### `random.binomial()`

This method is an other way to simulate a coin flip.

```r
np.random.binomial(10, 0.5, 1000000)
```

The example above will flip 10 coins (with a fair rate due to the 0.5), with a sample of 1 million.

The result of this methods is a "aggregation" of the success events, which means the output varies from 0 to 10.
