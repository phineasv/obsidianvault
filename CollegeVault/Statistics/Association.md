- Quantitative and Categorical varible
	- Find the category first (maybe the score based on adress)
	- Use mean and median. Large median difference usually infer to association.
	- [[Box Plot|Boxplot]] creation: To see the difference in 50% of data
	- [[Histogram]] to inspect overlapping
		- Histogram help see more closely the data, prevent bimodal distribution
```python
import pandas as pd
import seaborn as sns

students = pd.read_csv('student.csv')

## This data has columns (school, address, abscene, MomJob, FaJob, G3)

# List the G3 given the adress is Urban or 'U'
score_urban = students.G3[students.address == 'U']
score_rural = students.G3[students.address == 'R']

# Box plot 
sns.boxplot(data = students, x = 'adress', y = 'G3')

# Histogram using density instead of frequency
## Because if we usee the frequency, there will be hard to inspect due to difference in total number
plt.hist(score_urban, normed=True, aplha=0.5, label='U', color = 'blue')
plt.hist(score_rural, normed=True, aplha=0.5, label='R', color = 'red')
plt.legend()
plt.show()

```

- Quantitative variables
	- Scatter plot
```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

housing = pd.read_csv('housing.csv')
## This data has columns (price, type, sqfeet, beds, baths)

# Scatter plot
plt.scatter(x = housing.price, y = housing.sqfeet)
plt.xlabel('Rental Price')
plt.ylabel('Area (Feet)')
```

- Categorical variables
	- Using **contigency tables**
	- **Marginal proportion** is the proportion of respondents in each cateegory of a single question
		- E.g: Yes/ No of var 1
	- Chi - square is the difference between observed table and no associate expected table
		- $ChiSquare = sum((observed - expected)^2)$
		- For 2x2 table, ChiSquare > 4 is strongly associated
```python
import pandas as pd
import matplotlib.pyplot as plt
import scipy.stats
import numpy as np

df = pd.read_csv('file.csv')

var1_var2_freq = pd.crosstab(df.var1, df.var2)
print(var1_var2_freq)

# var1 |  no  |  yes  |
# var2 |      |       |
# -----|------|-------|
# no   |   a  |   c   |
# yes  |   b  |   d   |

var1_var2_prop = var1_var2_freq / len(df) #Crosstab but in proportion
# var1 |   no    |   yes   |
# var2              
# -----|---------|---------|
# no   |   0.x   |   0.z   |
# yes  |   0.y   |   0.w   |

# Marginal Proportion
var1_marginal = var1_var2_prop.sum(axis = 0)
print(var1_marginal)
# var1
# no : 0.x + 0.y
# yes : 0.z + 0.w 
# dtype: float64

var2_marginal = var1_var2_prop.sum(axis = 1)
print(var2_marginal)
# var2
# no : 0.x + 0.z
# yes : 0.y + 0.w 
# dtype: float64

# Expected proportion table if var1 doesn't associate with var2
# var1 |             no              |             yes             |
# var2              
# -----|-----------------------------|-----------------------------|
# no   |   (0.x + 0.y)*(0.x + 0.z)   |   (0.z + 0.w)*(0.x + 0.z)   |
# yes  |   (0.x + 0.y)*(0.y + 0.w)   |   (0.z + 0.w)*(0.y + 0.w)   |

## Multiply the proportion with total number will help find the frequency table

#Using scipy.stats.chi2_contigency to find no association expected frequency table 
chi2, pval, dof, expected = scipy.stats.chi2_contingency(var1_var2_freq)
print(np.round(expected))
print(chi2) # ChiSquare printout

```

- **Covariance** describes the strength of a linear relationship
	- **Only for linear relationship**
```python

covar_table = np.cov(var1, var2)

#       |     Var 1     |    Var 2 
# Var 1 | Variance (v1) | Covariance
# Var 2 | Covariance    | Variance (v2)
```

- **Correlation** is a scaled form of covariance
	- Range from -1 to +1
	- **Only for linear relationship**
	- corr = 0 for quardratic function
```python
from scipy.stats import pearsonr

corr_var1_var2, p = pearsonr(var1, var2)
print(corr_var1_var2)
```

- Other code
```python
# Group all the columns' mean based on each group of the 'column1'
df.groupby('column1').mean()
df.groupby('column1').median()

# Heatmap Correlation
colors = sns.diverging_palette(150, 275, as_cmap=True)
# Create heatmap using the .corr method on df, set colormap to cmap
sns.heatmap(rentals.corr(), center=0, cmap=colors)

#Pairplot
sns.pairplot(df)
plt.show()
```