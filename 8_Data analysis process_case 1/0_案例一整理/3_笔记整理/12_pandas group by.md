# pandas group by

了解有关 [Pandas Groupby](https://pandas.pydata.org/pandas-docs/stable/groupby.html) 的更多信息 并[在此](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.groupby.html) 查看其文档。

同时需要跟着视频练习合并的数据集。 

# 使用group by 得出结论

group by的用法在前面好像有讲到过，现在就是怎么使用来解决这个问题。在数据库中有group by, 这里的处理也是有点像数据库中的处理，group by 某一列，然后在对数据框进行调用函数。例如：

wine_df.groupby('quantity').describe()

也就是，按照质量等级进行分组，然后在对数据进行分析。可以groupby几个列。

视频中，如果不想以分组的列作为索引，可以

wine_df.groupby('quantity','color',as_index=False).mean()

