# 练习：DataFrame applymap()

## 练习：

```python
import pandas as pd

# Change False to True for this block of code to see what it does

# DataFrame applymap()
if True:
    df = pd.DataFrame({
        'a': [1, 2, 3],
        'b': [10, 20, 30],
        'c': [5, 10, 15]
    })
    
    def add_one(x):
        return x + 1
        
    print df.applymap(add_one)
    
grades_df = pd.DataFrame(
    data={'exam1': [43, 81, 78, 75, 89, 70, 91, 65, 98, 87],
          'exam2': [24, 63, 56, 56, 67, 51, 79, 46, 72, 60]},
    index=['Andre', 'Barry', 'Chris', 'Dan', 'Emilio', 
           'Fred', 'Greta', 'Humbert', 'Ivan', 'James']
)
print grades_df

#自己写一个函数在这里
def convert_grade(grade):
    if grade >= 90:
        return 'A'
    elif grade >= 80:
        return 'B'
    elif grade >= 70:
        return 'C'
    elif grade >= 60:
        return 'D'
    else:
        return 'F'
 print convert_grade(85)  
def convert_grades(grades):
    '''
    Fill in this function to convert the given DataFrame of numerical
    grades to letter grades. Return a new DataFrame with the converted
    grade.
    
    The conversion rule is:
        90-100 -> A
        80-89  -> B
        70-79  -> C
        60-69  -> D
        0-59   -> F
    '''
    return grades.applymap(convert_grade)

print convert_grades(grades_df)
```



思路：先转化为等级

执行以上代码输出结果：

```python
   a   b   c
0  2  11   6
1  3  21  11
2  4  31  16
         exam1  exam2
Andre       43     24
Barry       81     63
Chris       78     56
Dan         75     56
Emilio      89     67
Fred        70     51
Greta       91     79
Humbert     65     46
Ivan        98     72
James       87     60
B
        exam1 exam2
Andre       F     F
Barry       B     D
Chris       C     F
Dan         C     F
Emilio      B     D
Fred        C     F
Greta       A     C
Humbert     D     F
Ivan        A     C
James       B     D
```



### Pandas shift()

Pandas shift() 函数的文档可以在[这里](http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.shift.html)找到。如果你仍不确定函数的运行机制，请一边尝试一边了解！

- pandas.DataFrame.shift

- `DataFrame.``shift`(*periods=1*, *freq=None*, *axis=0*)[[source\]](http://github.com/pandas-dev/pandas/blob/v0.23.1/pandas/core/frame.py#L3800-L3803) 

  Shift index by desired number of periods with an optional time freq 

  使用可选的时间频率按期望的周期数移动索引

| Parameters: | **periods** : intNumber of periods to move, can be positive or negative**freq** : DateOffset, timedelta, or time rule string, optionalIncrement to use from the tseries module or time rule (e.g. ‘EOM’). See Notes.**axis** : {0 or ‘index’, 1 or ‘columns’} |
| ----------- | ------------------------------------------------------------ |
| Returns:    | **shifted** : DataFrame                                      |



### 另一种方法

还有一种方法是通过向量化运算，你还可以使用代码 `return entries_and_exits.diff()` 在单个步骤中计算答案。