# 访问 DataFrame 元素



实例：创建Dataframe

```python
# Change False to True for each block of code to see what it does

# DataFrame creation
if True:
    # You can create a DataFrame out of a dictionary mapping column names to values
    df_1 = pd.DataFrame({'A': [0, 1, 2], 'B': [3, 4, 5]})
    print df_1
    # You can also use a list of lists or a 2D NumPy array
    df_2 = pd.DataFrame([[0, 1, 2], [3, 4, 5]], columns=['A', 'B', 'C'])
    print df_2
```

以上是两种创建方法的输出结果：

```python
   A  B
0  0  3
1  1  4
2  2  5
   A  B  C
0  0  1  2
1  3  4  5
```

这个输出结果，两次显示的方向不一样



### 访问Dataframe元素

实例

```python
# Accessing elements
if True:
    print ridership_df.iloc[0] #访问第一行
    print ridership_df.loc['05-05-11'] #通过索引访问
    print ridership_df['R003'] #通过列访问
    print ridership_df.iloc[1, 3] #访问具体位置的元素
    
```

输出结果如下：

```python
R003    0
R004    0
R005    2
R006    5
R007    0
Name: 05-01-11, dtype: int64
R003    1608
R004    4802
R005    3932
R006    4477
R007    2705
Name: 05-05-11, dtype: int64
05-01-11       0
05-02-11    1478
05-03-11    1613
05-04-11    1560
05-05-11    1608
05-06-11    1576
05-07-11      95
05-08-11       2
05-09-11    1438
05-10-11    1342
Name: R003, dtype: int64
2328
```



### 访问多列元素

实例

```python
# Accessing multiple rows
if False:
    print ridership_df.iloc[1:4]
```



结果：

```python
          R003  R004  R005  R006  R007
05-02-11  1478  3877  3674  2328  2539
05-03-11  1613  4088  3991  6461  2691
05-04-11  1560  3392  3826  4787  2613
```

输出到3行截止，不输出4行

### 访问多列Dataframe

```python
# Accessing multiple columns
if True:
    print ridership_df[['R003', 'R005']] #列明之间逗号分隔
```

```python
          R003  R005
05-01-11     0     2
05-02-11  1478  3674
05-03-11  1613  3991
05-04-11  1560  3826
05-05-11  1608  3932
05-06-11  1576  3909
05-07-11    95   255
05-08-11     2     1
05-09-11  1438  3589
05-10-11  1342  4009
```

输出结果带有索引和列名

### 访问轴

```python
# Pandas axis
if False:
    df = pd.DataFrame({'A': [0, 1, 2], 'B': [3, 4, 5]})
    print df.sum()
    print df.sum(axis=1)
    print df.values.sum()
```



```python
A     3
B    12
dtype: int64
0    3
1    5
2    7
dtype: int64
15

```





```python
(R005    2718.8
R006    3239.9
dtype: float64, R005    4009
R006    6461
dtype: int64)
```

