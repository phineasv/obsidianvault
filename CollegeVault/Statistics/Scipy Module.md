```python
import scipy.stats
import numpy as np
import pandas as pd

df = pd.read_csv('file.csv')

scipy.stats.trim_mean(df['column'], 0.1) #Take out 10% of data's beginning and last part and find the mean

chi2, pval, dof, expected = scipy.stats.chi2_contingency(freq_table) # Create expected frequency table
print(np.round(expected))

```