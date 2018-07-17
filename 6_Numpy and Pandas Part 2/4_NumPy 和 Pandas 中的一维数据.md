# NumPy 和 Pandas 中的一维数据

pandas读取csv文件的速度更快。



读取文件实例：

```python
import unicodecsv
def read_csv(filename):
    with open(filename, 'rb') as f:
        reader = unicodecsv.DictReader(f)
    return list(reader)
daily_engagement = read_csv('C:\Users\Administrator\Desktop\lyfFolder\6_python_numpy\daily-engagement-full.csv')
```

导入过程会大概花一分钟，然后读取去重后的学生数据也需要一段时间



如果用pandas 会大大缩小运行的时间：

```python
import pandas as pd
daily_engagement = pd.read_csv('C:\Users\Administrator\Desktop\lyfFolder\6_python_numpy\daily-engagement-full.csv')
len(daily_engagement{'acct'}.unique)
```

这里读取文件会报出错误，原因是没有在同一目录下。