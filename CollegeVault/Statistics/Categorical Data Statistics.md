- **Nominal categorical variable**: No intrinsic ordering to the categories
	- Extract most common responses
	- Table of frequency:
		- Not include Nan
	- True = 1; False = 0 
		- Can use Mean on this
```python
# Most common responses with counts
# In other words, it return table of frequencies
counts = df['martial.status'].value_counts() 

# Extract the name of modals
modal_cat = counts.index[0]

# Find proportion of the frequence
## Method 1: Using /len()
proportion_table1 = df['martial.status'].value_counts()/len(df['martial.status']) 
## Method 2: Using normalize
proportion_table2 = df['martial.status'].value_counts(normalize = True, dropna = False)
	###dropna = False means it will count Nan
### All return the table of proportion
### There may be difference between two because of NaN Value

booleandata1 = ['Alive', 'Dead', 'Dead', 'Alive', 'Dead', 'Alive']
booleandata2 = [2, 5, 2, 1, 5, 6, 7]
# Turn list into DataFrame
df1 = pd.DataFrame(booleandata, columns = ['tree_status'])
df2 = pd.DataFrame(booleandata, columns = ['number'])
# Turn into binary 1 and 0 and count the sum and mean
alive_tree_frq = (df1.tree_status == 'Alive').sum() #3
alive_tree_pro = (df1.tree_status == 'Alive').mean() #0.5

num_more_3 = (df2.number > 3).sum()
```

- **Ordinal categorical variable**: have ordered categoris
	- Convert variable to type `category` using `pandas.Categorical()`
	- `category` type data has an attribute `cat.codes` which turn categorical data into numerical
		- Can use mean, median on it. 
		- However, mean is not interpretable since the data is not equal in terms of spacing
		- [[Variance and Standard Deviation]] depends on mean. ^534026
		- Can use [[Quartile and Percentile]] instead ^5ed07f
```python
import numpy as np
import pandas as pd

correct_order = ['1', '2', '3', '4', '5']

df['star'] = pandas.Categorical(df['star'], correct_order, ordered = True)

#Changing category data into numerical data using cat.codes
median_index = np.median(df['star'].cat.codes)
median_category = correct_order[int(median_index)]

# Using perecentile
p25_index = np.precentile(df['star'].cat.codes, 25)
p25_category = correct_order[int(p25_index)]
```

- 2 ways to visualize
	- [[Bar Chart]]
	- [[Pie Chart]] 