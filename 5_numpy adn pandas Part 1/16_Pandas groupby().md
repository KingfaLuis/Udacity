# Pandas groupby()



```python
import matplotlib.pyplot as plt
import numpy as np
import pandas as pd
import seaborn as sns

values = np.array([1, 3, 2, 4, 1, 6, 4])
example_df = pd.DataFrame({
    'value': values,
    'even': values % 2 == 0,
    'above_three': values > 3 
}, index=['a', 'b', 'c', 'd', 'e', 'f', 'g'])

# Change False to True for each block of code to see what it does

# Examine DataFrame
if True:
    print example_df
```



```python
  above_three   even  value
a       False  False      1
b       False  False      3
c       False   True      2
d        True   True      4
e       False  False      1
f        True   True      6
g        True   True      4
```



```python
# Examine groups
if True:
    grouped_data = example_df.groupby('even') #按照even列分组
    # The groups attribute is a dictionary mapping keys to lists of row indexes
    print grouped_data.groups
```



```python
{False: Index([u'a', u'b', u'e'], dtype='object'), True: Index([u'c', u'd', u'f', u'g'], dtype='object')}
```



通过多列分组

```python
# Group by multiple columns
if True:
    grouped_data = example_df.groupby(['even', 'above_three'])
    print grouped_data.groups
```



```python
{(True, False): Index([u'c'], dtype='object'), (False, False): Index([u'a', u'b', u'e'], dtype='object'), (True, True): Index([u'd', u'f', u'g'], dtype='object')}
```



```python
# Get sum of each group
if True:
    grouped_data = example_df.groupby('even')
    print grouped_data.sum()
```



```python
       above_three  value
even                     
False          0.0      5 #对应False值的和
True           3.0     16 #对应True值的和
```





```python
# Limit columns in result
if True:
    grouped_data = example_df.groupby('even')
    
    # You can take one or more columns from the result DataFrame
    print grouped_data.sum()['value']
    
    print '\n' # Blank line to separate results
    
    # You can also take a subset of columns from the grouped data before 
    # collapsing to a DataFrame. In this case, the result is the same.
    print grouped_data['value'].sum()
```



```python
even
False     5
True     16
Name: value, dtype: int64


even
False     5
True     16
Name: value, dtype: int64
```

两个语法的输出结果是一致的



## 练习

```python
filename = '/datasets/ud170/subway/nyc_subway_weather.csv'
subway_df = pd.read_csv(filename)

### Write code here to group the subway data by a variable of your choice, then
### either print out the mean ridership within each group or create a plot.
###在此编写代码，按照您选择的变量对地铁数据进行分组，然后打印出每组中的平均乘客数量或画出图形。

if False:
    grouped_data = subway_df.groupby('station')
    print grouped_data['EXITSn']
```

