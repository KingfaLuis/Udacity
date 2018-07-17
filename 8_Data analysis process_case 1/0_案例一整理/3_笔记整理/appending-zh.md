
# 附加数据
首先，导入所需数据包并加载 `winequality-red.csv`  和 `winequality-white.csv`。


```python
# 导入 numpy 和 pandas
import numpy as np
import pandas as pd
# 加载红葡萄酒和白葡萄酒数据集
red_df = pd.read_csv('winequality-red.csv')
white_df = pd.read_csv('winequality-white.csv')
```

## 创建颜色列
创建两个数组，长度与重复 “红” 或 “白” 值的红白葡萄酒数据框的行数相同。NumPy 提供了非常简单的功能。这是介绍 [NumPy 重复](https://docs.scipy.org/doc/numpy/reference/generated/numpy.repeat.html) 功能的文档。阅读之后请自己尝试一下。


```python
# 为红葡萄酒数据框创建颜色数组
color_red = np.repeat(red_df,2)
#我看了Numpy的文档使用函数因为报错，dataframe没有repeat，需要先将Dataframe转化为series
# 为白葡萄酒数据框创建颜色数组
color_white = 
```

将名为 ‘颜色’ 的新列设置到适当数组，将数组添加到红葡萄酒和白葡萄酒数据框中。下面的框是在红葡萄酒数据框中添加数组。


```python
red_df['color'] = color_red
red_df.head()
```

白葡萄酒数据框的步骤相同，使用 `head()` 确认更改。

## 用附加功能组合数据框
查看  [Pandas 附加]( https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.append.html) 功能文档，查看组合数据框的方法。（附加题：为什么不使用 [合并](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.merge.html) 法组合数据框？）如果还不明白，我将在稍后介绍。务必将你的工作保存在这个 notebook 内，因为稍后还要回来。


```python
# 附加数据框
wine_df = 

# 查看数据框，检查是否成功
wine_df.head()
```

## 保存已组合的数据集
将新组合的数据框保存为 `winequality_edited.csv`。务必设置 `index=False`，以避免保存未命名列！
