# NumPy 轴

要画出图形，就要理解轴。 python中的sum函数.sum(axis=1)中的axis的理解。

- axis = 0 表示按列的方向相加，
- axis = 1 表示按行的方向相加

实例

```python
import numpy as np

# Change False to True for this block of code to see what it does

# NumPy axis argument
if True:
    a = np.array([
        [1, 2, 3],
        [4, 5, 6],
        [7, 8, 9]
    ])
    
    print a.sum()
    print a.sum(axis=0)
    print a.sum(axis=1)
```

输出结果：

```python
45  #整个二维数组的元素相加
[12 15 18] #按照列的方向相加
[ 6 15 24] #按照行的方向相加
```

实例

```python
# Subway ridership for 5 stations on 10 different days
ridership = np.array([
    [   0,    0,    2,    5,    0],
    [1478, 3877, 3674, 2328, 2539],
    [1613, 4088, 3991, 6461, 2691],
    [1560, 3392, 3826, 4787, 2613],
    [1608, 4802, 3932, 4477, 2705],
    [1576, 3933, 3909, 4979, 2685],
    [  95,  229,  255,  496,  201],
    [   2,    0,    1,   27,    0],
    [1438, 3785, 3589, 4174, 2215],
    [1342, 4043, 4009, 4665, 3033]
])

def min_and_max_riders_per_day(ridership):
    '''
    Fill in this function. First, for each subway station, calculate the
    mean ridership per day. Then, out of all the subway stations, return the
    maximum and minimum of these values. That is, find the maximum
    mean-ridership-per-day and the minimum mean-ridership-per-day for any
    subway station.
    '''
    mean_daily_ridership = ridership.mean(axis=0)
    
    max_daily_ridership = mean_daily_ridership.max()     # Replace this with your code
    min_daily_ridership = mean_daily_ridership.min()    # Replace this with your code
    
    return (max_daily_ridership, min_daily_ridership)
```



输出结果：

```python
(60279.8064516129, 0.0)
```

输出结果和答案有些不一样，结果有点奇怪，后面回来在看看