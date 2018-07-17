# Pandas Series apply()函数的使用

### split()

你可以在[此处](https://docs.python.org/2/library/stdtypes.html#str.split) 找到有关 Python `split()` 函数的文档。

- apply() apply函数可以对DataFrame对象进行操作，既可以作用于一行或者一列的元素，也可以作用于单个元素。 
- 在清理数据中会使用到apply()和split()

```python
import pandas as pd

# Change False to True to see what the following block of code does

# Example pandas apply() usage (although this could have been done
# without apply() using vectorized operations)
if True:
    s = pd.Series([1, 2, 3, 4, 5])
    def add_one(x):
        return x + 1
    print s.apply(add_one)

names = pd.Series([
    'Andre Agassi',
    'Barry Bonds',
    'Christopher Columbus',
    'Daniel Defoe',
    'Emilio Estevez',
    'Fred Flintstone',
    'Greta Garbo',
    'Humbert Humbert',
    'Ivan Ilych',
    'James Joyce',
    'Keira Knightley',
    'Lois Lane',
    'Mike Myers',
    'Nick Nolte',
    'Ozzy Osbourne',
    'Pablo Picasso',
    'Quirinus Quirrell',
    'Rachael Ray',
    'Susan Sarandon',
    'Tina Turner',
    'Ugueth Urbina',
    'Vince Vaughn',
    'Woodrow Wilson',
    'Yoji Yamada',
    'Zinedine Zidane'
])
def reverse_name(name):
    split_name = names.split("  ")
    first_name = split_name[0]
    last_name = split_name[1]
    return last_name + ', ' + first_name
    
def reverse_names(names):
    '''
    Fill in this function to return a new series where each name
    in the input series has been transformed from the format
    "Firstname Lastname" to "Lastname, FirstName".
    
    Try to use the Pandas apply() function rather than a loop.
    '''
    return names.apply(reverse_name)
```



# Python split()方法

## 描述

Python **split()** 通过指定分隔符对字符串进行切片，如果参数 num 有指定值，则仅分隔 num 个子字符串

## 语法

split() 方法语法：

```python
str.split(str="", num=string.count(str)).
```

## 参数

- str -- 分隔符，默认为所有的空字符，包括空格、换行(\n)、制表符(\t)等。
- num -- 分割次数。

## 返回值

返回分割后的字符串列表。

## 实例

以下实例展示了split()函数的使用方法：

```python
#!/usr/bin/python

str = "Line1-abcdef \nLine2-abc \nLine4-abcd";
print str.split( );
print str.split(' ', 1 );
```

以上实例输出结果如下：

```python
['Line1-abcdef', 'Line2-abc', 'Line4-abcd']
['Line1-abcdef', '\nLine2-abc \nLine4-abcd']
```

## 练习

```python
import pandas as pd

# Change False to True to see what the following block of code does

# Example pandas apply() usage (although this could have been done
# without apply() using vectorized operations)
if True:
    s = pd.Series([1, 2, 3, 4, 5])
    def add_one(x):
        return x + 1
    print s.apply(add_one)
```



```python
0    2
1    3
2    4
3    5
4    6
dtype: int64
```

可以看出运行结果又索引

执行下面的语句，先打印输出数组

```python
names = pd.Series([
    'Andre Agassi',
    'Barry Bonds',
    'Christopher Columbus',
    'Daniel Defoe',
    'Emilio Estevez',
    'Fred Flintstone',
    'Greta Garbo',
    'Humbert Humbert',
    'Ivan Ilych',
    'James Joyce',
    'Keira Knightley',
    'Lois Lane',
    'Mike Myers',
    'Nick Nolte',
    'Ozzy Osbourne',
    'Pablo Picasso',
    'Quirinus Quirrell',
    'Rachael Ray',
    'Susan Sarandon',
    'Tina Turner',
    'Ugueth Urbina',
    'Vince Vaughn',
    'Woodrow Wilson',
    'Yoji Yamada',
    'Zinedine Zidane'
])
print names
def reverse_names(names):
    '''
    Fill in this function to return a new series where each name
    in the input series has been transformed from the format
    "Firstname Lastname" to "Lastname, FirstName".
    
    Try to use the Pandas apply() function rather than a loop.
    '''
    names.split()
    
    return names.apply(reverse_names)
```

输出结果是：

```python
0             Andre Agassi
1              Barry Bonds
2     Christopher Columbus
3             Daniel Defoe
4           Emilio Estevez
5          Fred Flintstone
6              Greta Garbo
7          Humbert Humbert
8               Ivan Ilych
9              James Joyce
10         Keira Knightley
11               Lois Lane
12              Mike Myers
13              Nick Nolte
14           Ozzy Osbourne
15           Pablo Picasso
16       Quirinus Quirrell
17             Rachael Ray
18          Susan Sarandon
19             Tina Turner
20           Ugueth Urbina
21            Vince Vaughn
22          Woodrow Wilson
23             Yoji Yamada
24         Zinedine Zidane
dtype: object
```



实例，先切分names数组的第一个字符串

```python
def reverse_name(name):
    split_name = names.split("  ")
    first_name = split_name[0]
    last_name = split_name[1]
    return last_name + ', ' + first_name
    
def reverse_name(name):
    return names.apply(reverse_name)
```

