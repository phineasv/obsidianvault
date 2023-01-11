- [[Box Plot]]

```python
import matplotlib.pyplot as plt
data = [1, 2, 3, 4]
plt.boxplot(data)

#If there are more than 1 dataset
data2 = [4, 5, 6, 7]
plt.boxplot([data, data2], labels = ['Data 1', 'Data 2'])

plt.show()
```

* Average, Mean, Median, Mode
```python
import numpy
import scipy.stats

data = [1, 2, 3, 4]
np.average(data)
np.mean(data)
np.median(data)
scipy.stats.mode(data)
```

* Standard
```python
import numpy as np

np.std(dataset)
```

* [[Quartile and Percentile]]
```python
import numpy as np
data = [1, 2, 3 ,4, 5, 6, 7]
np.quantile(data, 0.25)
# 0.25: 1st quantile
# 0.5: 2nd quantile
# 0.75: 3rd quantile

np.percentile(data, 80) # Range containing 80% of data
```

^ae19b0
