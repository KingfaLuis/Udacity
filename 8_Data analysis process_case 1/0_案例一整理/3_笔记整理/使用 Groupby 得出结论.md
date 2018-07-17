# 使用 Groupby 得出结论

在下面的notebook 中，你将使用 Pandas 的 [groupby](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.groupby.html) 函数调查有关此数据的两个问题。以下是回答每个问题的提示：

### 问题 1：某种类型的葡萄酒（红葡萄酒或白葡萄酒）是否代表更高的品质？

对于此问题，将红葡萄酒的平均质量与白葡萄酒的平均质量等级进行比较。要这样做，先按颜色分组，然后找到每组的平均质量等级。

### 问题 2：哪个水平的酸度（pH 值）获得的平均评级最高？

这个问题比较棘手，因为不同于`颜色`有明确的分类可以分组（红葡萄酒和白葡萄酒），`pH 值`是一个没有明确类别的定量变量。但是，有一个简单的解决方案。你可以通过创建自己的类别，从定量变量创建一个分类变量。[Pandas 的 cut](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.cut.html) 函数可以让你将数据"切分"为组。你可以使用它，创建具有以下类别的名为`acidity_levels`的新列：

#### 酸度水平：

1. 高: 最低 25% 时的 pH 值
2. 中等偏高: 25% - 50% 时的 pH 值
3. 中: 50% - 75% 时的 pH 值
4. 低: 最高 75% 时的 pH 值

在这里，数据在 25%、50% 和 75% 三个百分比处做了拆分。记住，你可以使用 Pandas 的 `describe()` 函数获得这些数字！创建这四个类别后，你可以使用 groupby 获得每个酸度水平的平均质量评级。