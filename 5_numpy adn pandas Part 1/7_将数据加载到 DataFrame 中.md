# 将数据加载到 DataFrame 中



- read_csv()
- head()

载入纽约地铁和天气的数据

```python
import pandas as pd
subway_df = pd.read_csv('nyc_subway_weather.csv')#添加纽约地铁和天气的数据
subway_df.head() 
subway_df.describe() #对数据进行描述
```

