# DataFrame 向量化运算



### Pandas shift()

Pandas shift() 函数的文档可以在[这里](http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.shift.html)找到。如果你仍不确定函数的运行机制，请一边尝试一边了解！

### pandas.DataFrame.shift

`DataFrame.``shift`(*periods=1*, *freq=None*, *axis=0*)[[source\]](http://github.com/pandas-dev/pandas/blob/v0.23.1/pandas/core/frame.py#L3800-L3803) 

Shift index by desired number of periods with an optional time freq 

| Parameters: | **periods** : int。 Number of periods to move, can be positive or negative。**freq** : DateOffset, timedelta, or time rule string, optionalIncrement to use from the tseries module or time rule (e.g. ‘EOM’). See Notes.**axis** : {0 or ‘index’, 1 or ‘columns’} |
| ----------- | ------------------------------------------------------------ |
| Returns:    | **shifted** : DataFrame                                      |

| 参数 | periods: 移动的周期数可以是正数或负数. freq：DateOffset，timedelta或时间规则字符串，要从tseries模块或时间规则使用的optionalIncrement（例如'EOM'）。 请参阅Notes.axis：{0或'index'，1或'columns'} |
| ---- | ------------------------------------------------------------ |
|      |                                                              |

### 实例

```python
entries_and_exits = pd.DataFrame({
    'ENTRIESn': [3144312, 3144335, 3144353, 3144424, 3144594,
                 3144808, 3144895, 3144905, 3144941, 3145094],
    'EXITSn': [1088151, 1088159, 1088177, 1088231, 1088275,
               1088317, 1088328, 1088331, 1088420, 1088753]
```



```python
print entries_and_exits.shift(1)
```



```python
    ENTRIESn     EXITSn
0        NaN        NaN #显示为NaN
1  3144312.0  1088151.0
2  3144335.0  1088159.0
3  3144353.0  1088177.0
4  3144424.0  1088231.0
5  3144594.0  1088275.0
6  3144808.0  1088317.0
7  3144895.0  1088328.0
8  3144905.0  1088331.0
9  3144941.0  1088420.0
```



```python
print entries_and_exits.shift(2)
```



```python
    ENTRIESn     EXITSn
0        NaN        NaN  #
1        NaN        NaN  #
2  3144312.0  1088151.0
3  3144335.0  1088159.0
4  3144353.0  1088177.0
5  3144424.0  1088231.0
6  3144594.0  1088275.0
7  3144808.0  1088317.0
8  3144895.0  1088328.0
9  3144905.0  1088331.0
```



### 另一种方法

还有一种方法是通过向量化运算，你还可以使用代码 `return entries_and_exits.diff()` 在单个步骤中计算答案。



### 实例

```python
import pandas as pd

# Examples of vectorized operations on DataFrames:
# Change False to True for each block of code to see what it does

# Adding DataFrames with the column names
if True:
    df1 = pd.DataFrame({'a': [1, 2, 3], 'b': [4, 5, 6], 'c': [7, 8, 9]})
    df2 = pd.DataFrame({'a': [10, 20, 30], 'b': [40, 50, 60], 'c': [70, 80, 90]})
    print df1 + df2
```





```python
    a   b   c
0  11  44  77
1  22  55  88
2  33  66  99
```



实例

```python
# Adding DataFrames with overlapping column names  #列
if True:
    df1 = pd.DataFrame({'a': [1, 2, 3], 'b': [4, 5, 6], 'c': [7, 8, 9]})
    df2 = pd.DataFrame({'d': [10, 20, 30], 'c': [40, 50, 60], 'b': [70, 80, 90]})
    print df1 + df2

```



和第一个运行结果相比

```python
    a   b   c
0  11  44  77
1  22  55  88
2  33  66  99 #第一个实例运行结果
    a   b   c   d
0 NaN  74  47 NaN #只加载索引对应的位置，其余的为空值，不保留原值
1 NaN  85  58 NaN
2 NaN  96  69 NaN
```



```python
# Adding DataFrames with overlapping row indexes #行
if True:
    df1 = pd.DataFrame({'a': [1, 2, 3], 'b': [4, 5, 6], 'c': [7, 8, 9]},
                       index=['row1', 'row2', 'row3'])
    df2 = pd.DataFrame({'a': [10, 20, 30], 'b': [40, 50, 60], 'c': [70, 80, 90]},
                       index=['row4', 'row3', 'row2'])  #对应的行顺序不一样
    print df1 + df2
```



```python
         a     b     c
row1   NaN   NaN   NaN
row2  32.0  65.0  98.0
row3  23.0  56.0  89.0
row4   NaN   NaN   NaN
```

指定对应的元素相加，不是两个数组的都有的就会标记为NaN



还有自己定义编写部分未完成。



```python
There was an error running your code:


Traceback (most recent call last):
  File "vm_main.py", line 33, in 
    import main
  File "/tmp/vmuser_bjdylprdnf/main.py", line 2, in 
    import aiMain
  File "/tmp/vmuser_bjdylprdnf/aiMain.py", line 129, in 
    correct, comment, feedback = get_feedback()
  File "/tmp/vmuser_bjdylprdnf/aiMain.py", line 122, in get_feedback
    test_correct, test_comment = test_case.grade(vectorized_operations)
  File "/tmp/vmuser_bjdylprdnf/aiMain.py", line 67, in grade
    student_result = student_lib.get_hourly_entries_and_exits(self.df)
  File "/tmp/vmuser_bjdylprdnf/vectorized_operations.py", line 44, in get_hourly_entries_and_exits
    return entries_and_exits.shift(periods=9,freq=1,axis=0)
  File "/usr/local/lib/python2.7/dist-packages/pandas/core/frame.py", line 2847, in shift
    axis=axis)
  File "/usr/local/lib/python2.7/dist-packages/pandas/core/generic.py", line 4858, in shift
    return self.tshift(periods, freq)
  File "/usr/local/lib/python2.7/dist-packages/pandas/core/generic.py", line 4951, in tshift
    new_data.axes[block_axis] = index.shift(periods, freq)
  File "/usr/local/lib/python2.7/dist-packages/pandas/indexes/base.py", line 1766, in shift
    type(self).name)
NotImplementedError: Not supported for type RangeIndex


```

