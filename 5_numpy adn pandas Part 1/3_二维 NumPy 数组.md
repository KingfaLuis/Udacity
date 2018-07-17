# 二维 NumPy 数组



二维数据结构在不同环境下的不同叫法

- python: 列表的列表
- Numpy: 2D array
- Pandas: DataFrame



Numpy: 二维数组获取元素的方法有所不同，

- 例如访问一行三列的元素，是a[1,3]，而不是a[1]**[3]**。
- mean(),std(),等函数，计算的是整个二维数组的算数平均值，和标准偏差，而不是区分行和列。



### 实例：创建二维数组

每一行和列分别代表不同的日期和车站

```python
import numpy as np

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
# Accessing elements
if False:
    print ridership[1, 3]
    print ridership[1:3, 3:5]
    print ridership[1, :]
```



```python
# Accessing elements
if True:
    print ridership[1, 3]
    print ridership[1:3, 3:5]	#输出这个区域的元素，不包括上限
    print ridership[1, :]  #打印第一行的元素
```

输出结果：

```python
2328
[[2328 2539]
 [6461 2691]]
[1478 3877 3674 2328 2539]
```

注意输出的结果中，每个结果是怎么得来的。

### 实例

```python
# Vectorized operations on rows or columns
if True:
    print ridership[0, :] + ridership[1, :]	#两行相加
    print ridership[:, 0] + ridership[:, 1]	#两列相加
```

相加的结果如下：

```python
[1478 3877 3676 2333 2539]
[   0 5355 5701 4952 6410 5509  324    2 5223 5385]
```

### 实例：两个二维数组相加

```python
# Vectorized operations on entire arrays
if True:
    a = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
    b = np.array([[1, 1, 1], [2, 2, 2], [3, 3, 3]])
    print a + b
```



```python
[[ 2  3  4]
 [ 6  7  8]
 [10 11 12]]
```

### 练习

```python
def mean_riders_for_max_station(ridership):
    '''
    Fill in this function to find the station with the maximum riders on the
    first day, then return the mean riders per day for that station. Also
    return the mean ridership overall for comparsion.
    
    Hint: NumPy's argmax() function might be useful:
    http://docs.scipy.org/doc/numpy/reference/generated/numpy.argmax.html
    '''
    overall_mean = ridership.mean() # Replace this with your code
    mean_for_max = np.argmax(ridership) # Replace this with your code
    
    return (overall_mean, mean_for_max)
```

输出结果：

```python
For the full subway dataset, your function returned: (10997.603726362626, 2336)
```

### 内存布局

[此页面](http://docs.scipy.org/doc/numpy/reference/arrays.ndarray.html#internal-memory-layout-of-an-ndarray) 介绍了 2D NumPy 数组的内存布局。



[1]: https://docs.scipy.org/doc/numpy/reference/arrays.ndarray.html#internal-memory-layout-of-an-ndarray	"内存布局"

