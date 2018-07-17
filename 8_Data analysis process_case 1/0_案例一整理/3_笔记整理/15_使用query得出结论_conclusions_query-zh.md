
# 用查询功能做出结论


```python
# 加载 `winequality_edited.csv`
import pandas as pd
df = pd.read_csv('winequality_edited.csv')
df.head()

```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>alcohol</th>
      <th>chlorides</th>
      <th>citric_acid</th>
      <th>color</th>
      <th>density</th>
      <th>fixed_acidity</th>
      <th>free_sulfur_dioxide</th>
      <th>pH</th>
      <th>quality</th>
      <th>residual_sugar</th>
      <th>sulphates</th>
      <th>total_sulfur-dioxide</th>
      <th>total_sulfur_dioxide</th>
      <th>volatile_acidity</th>
      <th>acidity_levels</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>9.4</td>
      <td>0.076</td>
      <td>0.00</td>
      <td>red</td>
      <td>0.9978</td>
      <td>7.4</td>
      <td>11.0</td>
      <td>3.51</td>
      <td>5</td>
      <td>1.9</td>
      <td>0.56</td>
      <td>34.0</td>
      <td>NaN</td>
      <td>0.70</td>
      <td>low</td>
    </tr>
    <tr>
      <th>1</th>
      <td>9.8</td>
      <td>0.098</td>
      <td>0.00</td>
      <td>red</td>
      <td>0.9968</td>
      <td>7.8</td>
      <td>25.0</td>
      <td>3.20</td>
      <td>5</td>
      <td>2.6</td>
      <td>0.68</td>
      <td>67.0</td>
      <td>NaN</td>
      <td>0.88</td>
      <td>mod_high</td>
    </tr>
    <tr>
      <th>2</th>
      <td>9.8</td>
      <td>0.092</td>
      <td>0.04</td>
      <td>red</td>
      <td>0.9970</td>
      <td>7.8</td>
      <td>15.0</td>
      <td>3.26</td>
      <td>5</td>
      <td>2.3</td>
      <td>0.65</td>
      <td>54.0</td>
      <td>NaN</td>
      <td>0.76</td>
      <td>medium</td>
    </tr>
    <tr>
      <th>3</th>
      <td>9.8</td>
      <td>0.075</td>
      <td>0.56</td>
      <td>red</td>
      <td>0.9980</td>
      <td>11.2</td>
      <td>17.0</td>
      <td>3.16</td>
      <td>6</td>
      <td>1.9</td>
      <td>0.58</td>
      <td>60.0</td>
      <td>NaN</td>
      <td>0.28</td>
      <td>mod_high</td>
    </tr>
    <tr>
      <th>4</th>
      <td>9.4</td>
      <td>0.076</td>
      <td>0.00</td>
      <td>red</td>
      <td>0.9978</td>
      <td>7.4</td>
      <td>11.0</td>
      <td>3.51</td>
      <td>5</td>
      <td>1.9</td>
      <td>0.56</td>
      <td>34.0</td>
      <td>NaN</td>
      <td>0.70</td>
      <td>low</td>
    </tr>
  </tbody>
</table>
</div>



### 酒精含量高的酒是否评分较高？


```python
# 获取酒精含量的中位数
# midle = df.loc[:,'alcohol'].describe().iloc[5]
df.alcohol.median()
```




    10.3




```python
# 选择酒精含量小于中位数的样本
low_alcohol = df[df.alcohol < 10.3]

# 选择酒精含量大于等于中位数的样本
high_alcohol = df[df.alcohol >= 10.3]

# 确保这些查询中的每个样本只出现一次
num_samples = df.shape[0]
num_samples == low_alcohol['quality'].count() + high_alcohol['quality'].count() # 应为真
```




    True




```python
# 获取低酒精含量组和高酒精含量组的平均质量评分
low_alcohol.quality.mean(),high_alcohol.quality.mean()
# df.head()
```




    (5.475920679886686, 6.1460843373493974)



### 口感较甜的酒是否评分较高？


```python
# 获取残留糖分的中位数
# df.head()
df.residual_sugar.median()
```




    3.0




```python
# 选择残留糖分小于中位数的样本
low_sugar =df[df.residual_sugar < 3.0]

# 选择残留糖分大于等于中位数的样本
high_sugar =df[df.residual_sugar >= 3.0]

# 确保这些查询中的每个样本只出现一次
num_samples == low_sugar['quality'].count() + high_sugar['quality'].count() # 应为真
```




    True




```python
# 获取低糖分组和高糖分组的平均质量评分
low_sugar.quality.median(),high_sugar.quality.median()
```




    (6.0, 6.0)


