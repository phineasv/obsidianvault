```python
import pandas as pd

df = pd.DataFrame(table)

# Create wedge size and labels
wedge_size = df['Proportions']
label_name = df['Column Name']

# Create the pie chart
plt.pie(wedge_size, labels = label_name)

# Set pie chart to be a perfect circle
plt.axis('equal')

# Set title and show it
plt.title('Title')
plt.show()
```
