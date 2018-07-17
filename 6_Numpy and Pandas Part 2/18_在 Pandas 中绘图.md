# 在 Pandas 中绘图

如果变量 `data` 是一个 NumPy 数组或 Pandas Series，就像它是一个列表一样，代码 

```python
import matplotlib.pyplot as plt
plt.hist(data)
```

将创建数据的直方图。

Pandas 库实际上已经内置了 matplotlib 库的绘图函数。也就是说，如果对 Pandas 库中的 Series 数据绘图，不用 import matplotlib 就能完成绘图，你可以使用 `data.hist()` 创建直方图。另外，例子中的 seaborn 也是一种绘图样式库。

在此情形中，这两者没有区别，但有时候 Pandas 封装器更加方便。例如，你可以使用 `data.plot()` 创建 Series 的线条图。Series 索引被用于 x 轴，值被用于 y 轴。

在随后的测试题中，我们创建了一个 Series，其中包含本节课所涉及到的各种变量。选择你感兴趣的国家，创建每个变量随时间变化的图形。

如果你在本地运行绘图代码，你可能会需要加入一行 `plt.show()` 代码。

http://pandas.pydata.org/pandas-docs/stable/visualization.html



```python
import pandas as pd
import seaborn as sns

# The following code reads all the Gapminder data into Pandas DataFrames. You'll
# learn about DataFrames next lesson.

path = '/datasets/ud170/gapminder/'
employment = pd.read_csv(path + 'employment_above_15.csv', index_col='Country')
female_completion = pd.read_csv(path + 'female_completion_rate.csv', index_col='Country')
male_completion = pd.read_csv(path + 'male_completion_rate.csv', index_col='Country')
life_expectancy = pd.read_csv(path + 'life_expectancy.csv', index_col='Country')
gdp = pd.read_csv(path + 'gdp_per_capita.csv', index_col='Country')

# The following code creates a Pandas Series for each variable for the United States.
# You can change the string 'United States' to a country of your choice.

employment_us = employment.loc['United States']
female_completion_us = female_completion.loc['United States']
male_completion_us = male_completion.loc['United States']
life_expectancy_us = life_expectancy.loc['United States']
gdp_us = gdp.loc['United States']

# Uncomment the following line of code to see the available country names
# print employment.index.values

# Use the Series defined above to create a plot of each variable over time for
# the country of your choice. You will only be able to display one plot at a time
# with each "Test Run".
```





```
['Afghanistan' 'Albania' 'Algeria' 'Angola' 'Argentina' 'Armenia'
 'Australia' 'Austria' 'Azerbaijan' 'Bahamas' 'Bahrain' 'Bangladesh'
 'Barbados' 'Belarus' 'Belgium' 'Belize' 'Benin' 'Bhutan' 'Bolivia'
 'Bosnia and Herzegovina' 'Botswana' 'Brazil' 'Brunei' 'Bulgaria'
 'Burkina Faso' 'Burundi' 'Cambodia' 'Cameroon' 'Canada' 'Cape Verde'
 'Central African Rep.' 'Chad' 'Chile' 'China' 'Colombia' 'Comoros'
 'Congo, Rep.' 'Congo, Dem. Rep.' 'Costa Rica' "Cote d'Ivoire" 'Croatia'
 'Cuba' 'Cyprus' 'Czech Rep.' 'Denmark' 'Dominican Rep.' 'Timor-Leste'
 'Ecuador' 'Egypt' 'El Salvador' 'Equatorial Guinea' 'Eritrea' 'Estonia'
 'Ethiopia' 'Fiji' 'Finland' 'France' 'Gabon' 'Gambia' 'Georgia' 'Germany'
 'Ghana' 'Greece' 'Guadeloupe' 'Guatemala' 'Guinea' 'Guinea-Bissau'
 'Guyana' 'Haiti' 'Honduras' 'Hong Kong, China' 'Hungary' 'Iceland'
 'India' 'Indonesia' 'Iran' 'Iraq' 'Ireland' 'Israel' 'Italy' 'Jamaica'
 'Japan' 'Jordan' 'Kazakhstan' 'Kenya' 'Korea, Dem. Rep.' 'Korea, Rep.'
 'Kuwait' 'Kyrgyzstan' 'Laos' 'Latvia' 'Lebanon' 'Lesotho' 'Liberia'
 'Libya' 'Lithuania' 'Luxembourg' 'Macao, China' 'Madagascar' 'Malawi'
 'Malaysia' 'Maldives' 'Mali' 'Malta' 'Martinique' 'Mauritania'
 'Mauritius' 'Mexico' 'Mongolia' 'Morocco' 'Mozambique' 'Myanmar'
 'Namibia' 'Nepal' 'Netherlands' 'Netherlands Antilles' 'New Zealand'
 'Nicaragua' 'Niger' 'Nigeria' 'Norway' 'Oman' 'Pakistan' 'Panama'
 'Papua New Guinea' 'Paraguay' 'Peru' 'Philippines' 'Poland' 'Portugal'
 'Puerto Rico' 'Qatar' 'Moldova' 'Reunion' 'Romania' 'Russia' 'Rwanda'
 'Saudi Arabia' 'Senegal' 'Serbia and Montenegro' 'Sierra Leone'
 'Singapore' 'Slovak Republic' 'Slovenia' 'Solomon Islands' 'Somalia'
 'South Africa' 'Spain' 'Sri Lanka' 'Sudan' 'Suriname' 'Swaziland'
 'Sweden' 'Switzerland' 'Syria' 'Taiwan' 'Tajikistan' 'Tanzania'
 'Thailand' 'Macedonia, FYR' 'Togo' 'Trinidad and Tobago' 'Tunisia'
 'Turkey' 'Turkmenistan' 'Uganda' 'Ukraine' 'United Arab Emirates'
 'United Kingdom' 'United States' 'Uruguay' 'Uzbekistan' 'Venezuela'
 'Vietnam' 'West Bank and Gaza' 'Yemen, Rep.' 'Zambia' 'Zimbabwe']

```

这结果可能有点问题，没有显示出图形