# Pandas —— 唯一值unique( )，计数值value_counts( )及成员资格isin( )

## 唯一值

```
In [141]: obj=pd.Series(['c','a','d','a','a','b','b','c','c','c'])

In [142]: obj.unique()
Out[142]: array(['c', 'a', 'd', 'b'], dtype=object)1234
```

## 计数值

```
In [143]: obj.value_counts()
Out[143]:
c    4
a    3
b    2
d    1
dtype: int641234567
```

## 成员资格

```
In [144]: obj.isin(['a','b'])
Out[144]:
0    False
1     True
2    False
3     True
4     True
5     True
6     True
7    False
8    False
9    False
dtype: bool12345678910111213
```

## 得到DataFrame相关列的柱状图

```
In [145]: data={'Q1':[1,3,4,4,4],'Q2':[2,3,2,2,3],'Q3':[1,5,2,4,4]}

In [146]: frame=pd.DataFrame(data)

In [147]: result=frame.apply(pd.value_counts).fillna(0)

In [150]: frame
Out[150]:
   Q1  Q2  Q3
0   1   2   1
1   3   3   5
2   4   2   2
3   4   2   4
4   4   3   4

In [151]: result
Out[151]:
    Q1   Q2   Q3
1  1.0  0.0  1.0
2  0.0  3.0  1.0
3  1.0  2.0  0.0
4  3.0  0.0  2.0
5  0.0  0.0  1.0
```