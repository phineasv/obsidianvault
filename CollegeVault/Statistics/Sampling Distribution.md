- How to create a sample
```python
import numpy as np

# Sample some random values
samp = np.random.choice(dataset, sample_size, replace = False)
## Replace false in order to avoid repetition of one value
```

- Central Limit Theorem (CLT)
> 	Sampling distribution of the mean is normally distributed as long as the population is not too skewed or the sample size is large enough. Usually n>30 is good.
> 	
> 	**Only applies for mean sampling distribution** 
- It means the mean of the population distribution is approximately equal the mean of mean distribution (if sampling about 500 times the sampling that has more than 30 values) or (if the population distribution is not too skewed)

CLT break-up:
	Sample size $n$ (n > 30) with mean $x$ and standard Deviation $\sigma$
	Population mean $\mu$
>  Mean $x$ approximately equal to the population mean $\mu$
>  $Sampling\ Distribution\ St.Dev=\frac{\sigma}{\sqrt(n)}$

- The standard deviatioon of a sampling distribution  is also know as *standard error* or *estimate of the mean*
	- As sample size increase, the standard error decreases
	- Population standard deviation increases, so will the standard error

- Mean is *Unbiased estimator*
- Maximum is *Biased estimator*, cuz the mean of the sampling distribution  of the maximum is not centered at the population maximum

- Probability
	- Using [[Probability#^3f4466|CDF]] with mean (equal to population mean) and standard error
```python
x = 75  
mean = 60  
std_dev = 40  
samp_size = 10  
standard_error = std_dev / (samp_size**.5)  
# remember that **.5 is raising to the power of one half, or taking the square root  
  
stats.norm.cdf(x,mean,standard_error)
```

- Variance of the sample
$$Variance=\frac{\sum(observation - sample\ mean)^2}{n-1}$$
- By using this formula, variance becom an unbiased estimator
```python 
import numpy as np

np.var(x, ddof = 1)
```