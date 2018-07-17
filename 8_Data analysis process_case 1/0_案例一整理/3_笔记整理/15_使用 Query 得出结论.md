# 15_使用 Query 得出结论

在下面的notebook 中，你将使用 [Pandas 的 query](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.query.html) 函数调查有关此数据的两个问题。以下是回答每个问题的提示：

### 问题 1：酒精含量越高的葡萄酒获得的评级更高吗？

要回答这个问题，请使用 query 创建两组葡萄酒样本:

1. 低酒精（酒精含量低于中值的样本）
2. 高酒精（酒精含量高于或等于中值的样本）

然后，找到每组的平均质量评级。

### 问题 2：更甜的葡萄酒（残糖更多）获得的评级更高吗？

同样，使用中值按残糖将样本分为两组，并找出每组的平均质量评级。

# 用查询功能做出结论

```python
# 加载 `winequality_edited.csv`
import pandas as pd
df = pd.read_csv('winequality_edited.csv')
df.head()

```

### 酒精含量高的酒是否评分较高？

```python
# 获取酒精含量的中位数
# midle = df.loc[:,'alcohol'].describe().iloc[5]
df.alcohol.median()
```

```
10.3
```



```python
# 选择酒精含量小于中位数的样本
low_alcohol = df[df.alcohol < 10.3]

# 选择酒精含量大于等于中位数的样本
high_alcohol = df[df.alcohol >= 10.3]

# 确保这些查询中的每个样本只出现一次
num_samples = df.shape[0]
num_samples == low_alcohol['quality'].count() + high_alcohol['quality'].count() # 应为真
```



```
True
```



```python
# 获取低酒精含量组和高酒精含量组的平均质量评分
low_alcohol.quality.mean(),high_alcohol.quality.mean()
# df.head()
```



```
(5.475920679886686, 6.1460843373493974)
```



### 口感较甜的酒是否评分较高？

```python
# 获取残留糖分的中位数
# df.head()
df.residual_sugar.median()
```



```
3.0
```



```python
# 选择残留糖分小于中位数的样本
low_sugar =df[df.residual_sugar < 3.0]

# 选择残留糖分大于等于中位数的样本
high_sugar =df[df.residual_sugar >= 3.0]

# 确保这些查询中的每个样本只出现一次
num_samples == low_sugar['quality'].count() + high_sugar['quality'].count() # 应为真
```



```
True
```



```python
# 获取低糖分组和高糖分组的平均质量评分
low_sugar.quality.mean(),high_sugar.quality.mean()
```



```
(5.8088007437248219, 5.8278287461773699)
```

这里得出的平均质量分一样的，

回答

### 习题 1/2

酒精含量越高的葡萄酒获得的评级更高吗？

- [x] 是
- [ ] 否

### 习题 2/2

更甜的葡萄酒获得的评级更高吗？

- [x] 是
- [ ] 否

#### 辅助材料

[ Conclusions-Query-Solutions](https://s3.amazonaws.com/video.udacity-data.com/topher/2018/June/5b307dbb_conclusions-query-solutions/conclusions-query-solutions.zip)

