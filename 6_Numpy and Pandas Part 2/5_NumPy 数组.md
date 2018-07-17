# NumPy 数组

## 一维数据结构

| panda                | Numpy  |
| -------------------- | ------ |
| series               | array  |
| j建立在numpy数组之上 | 更简单 |
| 有更多的特征         |        |

## numpy 数组和python 列表的对比

| 相同点             | 不同点                       |
| ------------------ | ---------------------------- |
| 通过元素位置访问   | 每个元素应该有相同的数据类型 |
| 访问指定范围的元素 | 有很多方便使用的函数         |
| 可以使用循环遍历   | numpy数组可以是多维的        |

### 实例：

```python
import numpy as np

# First 20 countries with employment data
countries = np.array([
    'Afghanistan', 'Albania', 'Algeria', 'Angola', 'Argentina',
    'Armenia', 'Australia', 'Austria', 'Azerbaijan', 'Bahamas',
    'Bahrain', 'Bangladesh', 'Barbados', 'Belarus', 'Belgium',
    'Belize', 'Benin', 'Bhutan', 'Bolivia',
    'Bosnia and Herzegovina'
])

# Employment data in 2007 for those 20 countries
employment = np.array([
    55.70000076,  51.40000153,  50.5       ,  75.69999695,
    58.40000153,  40.09999847,  61.5       ,  57.09999847,
    60.90000153,  66.59999847,  60.40000153,  68.09999847,
    66.90000153,  53.40000153,  48.59999847,  56.79999924,
    71.59999847,  58.40000153,  70.40000153,  41.20000076
])
```

#### 访问元素：

```python
if True:
    print countries[0]
    print countries[3]
```

#### 输出结果：

```python
Afghanistan
Angola
```

#### 切片访问指定范围内的元素

```python
# Slicing
if True:
    print countries[0:3]
    print countries[:3]
    print countries[17:]
    print countries[:]
```

#### 输出结果：

```python
['Afghanistan' 'Albania' 'Algeria']
['Afghanistan' 'Albania' 'Algeria']
['Bhutan' 'Bolivia' 'Bosnia and Herzegovina']
['Afghanistan' 'Albania' 'Algeria' 'Angola' 'Argentina' 'Armenia'
 'Australia' 'Austria' 'Azerbaijan' 'Bahamas' 'Bahrain' 'Bangladesh'
 'Barbados' 'Belarus' 'Belgium' 'Belize' 'Benin' 'Bhutan' 'Bolivia'
 'Bosnia and Herzegovina']
```

输出指定范围内的元素



#### 检查元素类型

```python
# Element types
if True:
    print countries.dtype
    print employment.dtype
    print np.array([0, 1, 2, 3]).dtype
    print np.array([1.0, 1.5, 2.0, 2.5]).dtype
    print np.array([True, False, True]).dtype
    print np.array(['AL', 'AK', 'AZ', 'AR', 'CA']).dtype
```



#### 输出结果：

```python
|S22
float64
int64
float64
bool
|S2
```



#### 通过for循环遍历：

```python
# Looping
if True:
    for country in countries:
        print 'Examining country {}'.format(country)

    for i in range(len(countries)):
        country = countries[i]
        country_employment = employment[i]
        print 'Country {} has employment {}'.format(country,
                country_employment)

```

输出结果：检查每个国家以及该过的就业率

```python
Examining country Afghanistan
Examining country Albania
Examining country Algeria
Examining country Angola
Examining country Argentina
Examining country Armenia
Examining country Australia
Examining country Austria
Examining country Azerbaijan
Examining country Bahamas
Examining country Bahrain
Examining country Bangladesh
Examining country Barbados
Examining country Belarus
Examining country Belgium
Examining country Belize
Examining country Benin
Examining country Bhutan
Examining country Bolivia
Examining country Bosnia and Herzegovina
Country Afghanistan has employment 55.70000076
Country Albania has employment 51.40000153
Country Algeria has employment 50.5
Country Angola has employment 75.69999695
Country Argentina has employment 58.40000153
Country Armenia has employment 40.09999847
Country Australia has employment 61.5
Country Austria has employment 57.09999847
Country Azerbaijan has employment 60.90000153
Country Bahamas has employment 66.59999847
Country Bahrain has employment 60.40000153
Country Bangladesh has employment 68.09999847
Country Barbados has employment 66.90000153
Country Belarus has employment 53.40000153
Country Belgium has employment 48.59999847
Country Belize has employment 56.79999924
Country Benin has employment 71.59999847
Country Bhutan has employment 58.40000153
Country Bolivia has employment 70.40000153
Country Bosnia and Herzegovina has employment 41.20000076
```



#### Numpy 功能实例：

输出均值，标准差，最大值以及总和

```python
# Numpy functions
if True:
    print employment.mean()
    print employment.std()
    print employment.max()
    print employment.sum()
```

#### 输出结果：

```python
58.68500003850001
9.338269113687888
75.69999695
1173.70000077
```

