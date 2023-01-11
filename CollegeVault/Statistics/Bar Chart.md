- Visualize using **seaborn** which is built off of the Mathplotlib library
```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# Create the DataFrame
df = pd.DataFrame(file)
num = df[2, 4, 5, 16, 3]
labels = df['A', 'B', 'C', 'D', 'E']

#Create Bar Chart of a column using sns
sns.countplot(x = df['column 1'], order = df['column 1'].value_counts(ascending = True).index) ## Bar from lowest to highest
plt.show()
## Can also use plt.barplot() 

sns.barplot(labels, num) # Create bar plot with error bars


```

