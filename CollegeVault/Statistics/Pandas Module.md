
```python
import pandas as pd

df = pd.read_csv('data.csv')
print(df['Column 1'].unique()) # See all unique value of the dataset

listofvalues = df['Column 1'].values # Return a list of all the values in the DataFrame

listofkey = df.columns.tolist() # Return list of all column headers

df['column'].replace({'True' : 1, 'False': 0}, inplace = True) # Replace elements in a column

df.describe(include = 'all') # Information and summary about the DataFrame

```