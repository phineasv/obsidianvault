- Using matplotlib.pyplot
```python
import matplotlib.pyplot as plt

df_column_mean = df.column.mean()

#Create a histogram
plt.hist(df['column'], bins = 20)

#Create a line that go through median
plt.vlines(x = df_column_mean, ymin=0, ymax=1300, colors='k', label='mean')
```

- Using seaborn
```python
import seaborn as sns

# Create a hiistogram
sns.distplot(df.column, kde = False) #Sns automatically assign bins based on data whereas plt default is 10
```
