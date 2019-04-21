# Probability Distributions

Distribution can be thought as a function that describes the relationship between observations in a sample space. It can be used to calculate the probability of any individual observation from the sample space.

### Density Functions

Distributions are often described in terms of their density functions. 

Types of Density Functions:

* **Probability Density function**: calculates the probability of observing a given value.
* **Cumulative Density function**: calculates the probability of an observation equal or less than a value.

Note: Both PDF and CDF are continuous functions. The equivalent of a PDF for a discrete distribution is called a probability mass function, or PMF.

### Gaussian \(Normal\) Distribution

Gausian distribution represents the behavior of most of the situations in the universe. It is so widely found in nature, hence the name Normal distribution.

**Characteristics:**

* The mean, median and mode of the distribution coincide
* The curve of the distribution is **bell-shaped** and symmetrical about the line x=μ
* The total area under the curve is 1
* Exactly half of the values are to the left of the center and the other half to the right

$$
P(x) = \frac{1}{{\sigma \sqrt {2\pi } }}e^{-(x-\mu)^2/2\sigma^2}
$$

### Bernoulli Distribution

 A **Bernoulli distribution** has only two possible outcomes, namely 1 \(success\) and 0 \(failure\), and a **single trial**. 

The Bernoulli distribution has only **one** parameter - the probability of success. 

Bernoulli Distribution is a special case of Binomial Distribution with a single trial.

### Binomial Distribution

A binomial experiment is simply sum of n independent Bernoulli's distribution which actually is a success/ failure experiment.

The binomial distribution has **two** parameters - the probability of success and the number of random variables

**Characteristics:**

* Each trial is independent
* There are only two possible outcomes in a trial- either a success or a failure
* A total number of n identical trials are conducted

### Chi-Squared Distribution

 The Chi Square $${\chi}^2$$ distribution is the distribution of the sum of squared standard normal deviates. 

The chi-square independence test is a procedure for testing if two categorical variables are related.

$$
\chi^2 = \Sigma {\frac{(Observed-Expected)^2}{Expected}}
$$

**Characteristics:**

* The mean of the distribution is equal to the number of degrees of freedom: μ = v. Note: The degrees of freedom of an estimate is the number of independent pieces of information that go into the estimate.
* The variance is equal to two times the number of degrees of freedom: $$σ^2 = 2 * v$$ 
* When the degrees of freedom are greater than or equal to 2, the maximum value for Y occurs when $${\chi}^2 = v - 2$$ .
* As the degrees of freedom increase, the chi-square curve approaches a normal distribution.

### Poisson Distribution

Poisson Distribution is applicable in situations where events occur at random points of time and space wherein our interest lies only in the number of occurrences of the event.

Examples:

1. The number of suicides reported in a particular city.
2. The number of printing errors at each page of the book.

**Characteristics:**

* Any successful event should not influence the outcome of another successful event
* The probability of success over a short interval must equal the probability of success over a longer interval.
* The probability of success in an interval approaches zero as the interval becomes smaller.

### Exponential Distribution

Exponential distribution is widely used for survival analysis. From the expected life of a machine to the expected life of a human, exponential distribution successfully delivers the result.



Link:  
- [https://www.analyticsvidhya.com/blog/2017/09/6-probability-distributions-data-science/](https://www.analyticsvidhya.com/blog/2017/09/6-probability-distributions-data-science/)  
- [https://machinelearningmastery.com/statistical-data-distributions/](https://machinelearningmastery.com/statistical-data-distributions/)  


