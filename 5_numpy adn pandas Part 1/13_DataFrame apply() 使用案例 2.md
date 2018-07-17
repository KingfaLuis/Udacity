# DataFrame apply() 使用案例 2



### 实例

```python
import numpy as np
import pandas as pd

df = pd.DataFrame({
    'a': [4, 5, 3, 1, 2],
    'b': [20, 10, 40, 50, 30],
    'c': [25, 20, 5, 15, 10]
})

# Change False to True for this block of code to see what it does

# DataFrame apply() - use case 2
if True:   
    print df.apply(np.mean)
    print df.apply(np.max)
```



```python
a     3.0
b    30.0
c    15.0
dtype: float64
a     5
b    50
c    25
dtype: int64
```



**一般会误认为**：能不能删除最大的，重新建立一个Dataframe，重新求出最大。但是pandas不会这么处理。

- 不会创建一个新的Dataframe，而是创建一个新的series。Dataframe转化成一个单值。
- 如果我想得到每一列的最大值，我可以调用df.apply(np.max),从而在DataFrame上的每一列调用numpy的最大值函数。在这种情况下，它的的结果等于内置函数df.max.在这种情况下,使用内置函数比较简单。
- 如果df.max不能满足你的要求，apply就非常的有用了。例如你要求出每一列的第二个最大值。
- 先建立一个单列，求出第二大，对单列进行排序。然后求出第二个。

[pandas.DataFrame.sort_values](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.sort_values.html)链接中有排序的的实例演示,理解参数的使用方法，以及函数返回值类型

- accending  =  false，默认为降序排列

```python
def second_largest_in_column(column):
    sorted_column = column.sort_valuse(ascending=False) #默认为降序排列
    return sorted_column.iloc[1]
print second_largest_in_column(df['a'])
```

检查输出的结果

```python
4
```



```python
def second_largest(df):
    return df.apply(second_largest_in_column)
```



### 实例的全部代码

```python
import numpy as np
import pandas as pd

df = pd.DataFrame({
    'a': [4, 5, 3, 1, 2],
    'b': [20, 10, 40, 50, 30],
    'c': [25, 20, 5, 15, 10]
})

# Change False to True for this block of code to see what it does

# DataFrame apply() - use case 2
if True:   
    print df.apply(np.mean)
    print df.apply(np.max)
    
def second_largest_in_column(column):
    sorted_column = column.sort_values(ascending=False)
    return sorted_column.iloc[1]

def second_largest(df):
    '''
    Fill in this function to return the second-largest value of each 
    column of the input DataFrame.
    '''
    
    return df.apply(second_largest_in_column)
    
print df.apply(second_largest_in_column)
```

以上代码输出结果：

```python
a     3.0
b    30.0
c    15.0
dtype: float64
a     5
b    50
c    25
dtype: int64
a     4
b    40
c    20
dtype: int64
```

