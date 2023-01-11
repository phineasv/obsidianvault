- Independence and Dependence
	- Throwing two dices: Independent events since the first dice doesn't affect second dice
	- 2 red marbles and 3 blue marbles in the bag: Dependent events

- Mutually Exclusive Events
	- When 2 events can't happen at the same time, they are mutually exclusive. E.g: "Tail" and "head"
	- When they can happen at the sam time, they are not mutually exclusive. E.g: "Odd number" and "Larger than 2"

- Rule of Addition
		- P(A): Probability of having Event A
		- P(B): Probability of having Event B
		- P(A or B) = P(A) + P(B) - P(A and B) if A is not mutually exclusive from B
		- P(A or B) = P(A) + P(B) if A is mutually exclusive from B

- Conditional Probability:
	- Probability of one event happen, given the another one already occured. Usually pair of dependent events
	- Pick 2 marbles from group of blue and red marbles. If the first marble is blue, what is P of red marble on the second try
	- Notation: $P(Red Second | Blue First)$
	- For independent events:
		- $P(A|B) = P(A)$ and $P(B|A) = P(B)$

- Multiplication
	- General Formula: $P(A and B) = P(A) . P(B|A)$
	- For independent Events: $P(A and B) = P(A) . P(B)$

- Bayes' Theorem
	- Use to find P(A|B) given the tree diagram
$$P(B|A)=\frac{P(A|B).P(B)}{P(A)}$$

# Probability Distribution
```python
# Create random variable from dice

die_6 = range(1, 7)
nums_roll = 5 # How many times the dice roll

## Create dice
np.random.choice(die_6, nums_roll, replace=True) ##Replace parameter means whether we want to keep thee value
```

- Probability Mass Functions: Type of probability distribution observing a particular value of discrete random variable. E.g: PMF to calculate the probability of rolling a three on a fair six-sided cube.
	- PMF IS NOT BINOMIAL DISTRIBUTION BUT RATHER FROM BINOMIAL DISTRIBUTION, USING PMF TO FIND A PROBABILITY
```python
import scipy.stats
print(scipy.stats.pmf(6, 10, 0.5))
# 6: 6 heads
# 10: 10 times
# 0.5: p each trial
```
- PMF over a range: 
	- Just sum everything. E.g: P(between 3 and 5 heads over 7 times) = P(3) + P(4) + P(5)

- Cumulative Distribution Function
	- $If\ x_1 < x_2 \rightarrow CDF(x_1) < CDF(x_2)$
![[Screen Shot 2022-12-28 at 9.38.11 PM.png]]
```python
import scipy.stats

print(scipy.stats.binom.cdf(6, 10, 0.5))

prob_6_to_8 = scipy.stats.binom.cdf(6, 10, 0.5) + scipy.stats.binom.cdf(7, 10, 0.5) + scipy.stats.binom.cdf(8, 10, 0.5)
```

- Probability Density Function
	- PMF for continuous random variables
```python
import scipy.stats
  
# stats.norm.cdf(x, loc, scale)  
print(scipy.stats.norm.cdf(158, 167.64, 8))
# x: value of interest
# loc: Mean of the probability distribution
# scale: Standard Deviation of the distribution
```

^3f4466

- Poisson probability distribution
	- Variance is equivalent to lambda. Means if lambda is larger, variance is larger
```python
import scipy.stats

print(scipy.stats.poisson.pmf(6, 10))
# probability of observing = 6, expected value or lambda = 10

print(scipy.stats.poisson.cdf(6,10))

# Create random poisson data
rvs = scipy.stats.poisson.rvs(10, size = 1000)
# Parameter: lambda,size = num_values
# return: list of random numbers

# Find mean 
print(rvs.mean())

# Find Variance
print(np.var(rand_vars))

# At which value that put us in a percentile of the Poisson distribution
scipy.stats.poisson.ppf(percentile, lambda)
```

- **Expected value** of binomial distribution
	- When flip a coin 10 times, we expect to see head 5
	- $Expected(of\ Heads) = E(X) = n * p=10*0.5=5$
- **Variance** of binomial distribution
	- $Variance(of\ something)=Var(X)=n*p*(1-p)$
	- e.g: $Variance(of\ Heads) = E(X) = n * p * (1-p)=10*0.5*(1-0.5)=2.5$

- Properties of Expctation and Variance (of all distribution)
	- $E(X+Y)=E(X)+E(Y)$
	- $E(aX) = aE(X)$
	- $E(X+a) = E(X)+a$
	- $Var(X+a)=Var(X)$
	- $Var(aX)=a^2Var(X)$
	- $Var(X+Y)=Var(X)+Var(Y)$ (Only X and Y are independent random variables)
