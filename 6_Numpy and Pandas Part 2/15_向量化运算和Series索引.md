# 15_向量化运算和Series索引



```python
import pandas as pd

# Change False to True for each block of code to see what it does

# Addition when indexes are the same
#两个索引值相同的相加
if True:
    s1 = pd.Series([1, 2, 3, 4], index=['a', 'b', 'c', 'd'])
    s2 = pd.Series([10, 20, 30, 40], index=['a', 'b', 'c', 'd'])
    print s1 + s2

# Indexes have same elements in a different order
#两个索引值不想相同的相加
if True:
    s1 = pd.Series([1, 2, 3, 4], index=['a', 'b', 'c', 'd'])
    s2 = pd.Series([10, 20, 30, 40], index=['b', 'd', 'a', 'c'])
    print s1 + s2

# Indexes overlap, but do not have exactly the same elements
if True:
    s1 = pd.Series([1, 2, 3, 4], index=['a', 'b', 'c', 'd'])
    s2 = pd.Series([10, 20, 30, 40], index=['c', 'd', 'e', 'f'])
    print s1 + s2

# Indexes do not overlap
#相加的索引完全不相同，相加后为空值
if True:
    s1 = pd.Series([1, 2, 3, 4], index=['a', 'b', 'c', 'd'])
    s2 = pd.Series([10, 20, 30, 40], index=['e', 'f', 'g', 'h'])
    print s1 + s2
```



```python
a    11
b    22
c    33
d    44
dtype: int64
a    31
b    12
c    43
d    24
dtype: int64
a     NaN
b     NaN
c    13.0
d    24.0
e     NaN
f     NaN
dtype: float64
a   NaN
b   NaN
c   NaN
d   NaN
e   NaN
f   NaN
g   NaN
h   NaN
dtype: float64
```

