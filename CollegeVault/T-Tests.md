- One of the test for [[Hypothesis Testing]]

- Scenario: A school has 1000 students who have the average score of 5.7. Pick a sample of 30 students to attend extra class, and their average score is 6. 

- Step 1: Ask a question: Are those students really outperform their peers?
- Step 2: Hypothesis
	- Null Hypothesis: 30 students are random sample from the general population of test takers that have average score of 5.7
	- Alternative Hypothesis:  30 students are random sample from the general population of test takers that have average score different from 5.7
- Step 3: Null Distribution 
	- Using [[Sampling Distribution#^088e43|Central Limit Theorem]] to make a distribution table of average grade
	- e.g:![[Screenshot 2023-01-15 at 7.39.18 PM.png]]
- Calculate a P-Value (or Confidence Interval)
	- Question: Given that the null value is true, how likely for 30 students to get 6. Since probability for exact score is small, we use three possible altenative hypotheses
	- Option 1: The sample of 30 comes from a population with average score > 5.7
	![[Screenshot 2023-01-15 at 7.45.18 PM.png]]

	- Option 2: The sample of 30 comes from a population with average score not equal to 5.7
	![[Screenshot 2023-01-15 at 7.46.19 PM.png]]

	- Option 3: The sample of 30 comes from a population with average score lower than 5.7
	![[Screenshot 2023-01-15 at 7.47.58 PM.png]]

- Step 5: Interpret the Results
	- p-values of 3 options (0.031, 0.062 and 0.969)
	- If they are chosen from 5.7 pts population, there is 3.1% chance of their average score being 6 pts or higher ==> Relatively unlikely

- Code
```python
import numpy as np
import scipy.stats

population_mean = 5.7
# Create a list of sample (list of 30 students' grade)
sample_list = np.readfromtxt("score.csv")
# Find the mean
score_mean = sample
# Perform one-sample t-test
tstat, pval = scipy.stats.ttest_1samp(sample_list, population_mean)
```

- Assumptions:
	- Sample was randomly selected from the population
	- Individual observation is independent
	- Inviting people to buy the pizza willl affect the hypothesis
	- Data is normally distribute without outlier OR sample size is large enough