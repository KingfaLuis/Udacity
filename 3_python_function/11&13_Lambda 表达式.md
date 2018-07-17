# Lambda 表达式

你可以使用 Lambda 表达式创建匿名函数，即没有名称的函数。lambda 表达式非常适合**快速创建**在代码中以后不会用到的函数。尤其对**高阶函数**或将其他函数作为参数的函数来说，非常实用。

我们可以使用 lambda 表达式将以下函数

```
def multiply(x, y):
    return x * y
```

简写为：

```
double = lambda x, y: x * y
```

### Lambda 函数的组成部分

1. 关键字 `lambda` 表示这是一个 lambda 表达式。
2. `lambda` 之后是该匿名函数的一个或多个参数（**用英文逗号分隔**），然后是一个**英文冒号** `:`。和函数相似，lambda 表达式中的参数名称是**随意的**。
3. 最后一部分是被评估并在该函数中返回的表达式，和**你可能会在函数中看到的 return 语句很像**。

鉴于这种结构，lambda 表达式**不太适合复杂的函数**，但是非常适合简短的函数。

# 练习：Lambda 与 Map

`map()` 是一个高阶内置函数，接受函数和可迭代对象作为输入，并返回一个将该函数应用到可迭代对象的每个元素的迭代器。下面的代码使用 `map()` 计算 `numbers` 中每个列表的**均值**，并**创建列表** `averages`。测试运行这段代码，看看结果如何。

通过将 `mean` 函数替换为在 `map()` 的调用中定义的 lambda 表达式，重写这段代码，使代码更简练。

```
numbers = [
              [34, 63, 88, 71, 29],
              [90, 78, 51, 27, 45],
              [63, 37, 85, 46, 22],
              [51, 22, 34, 11, 18]
           ]

def mean(num_list):
    return sum(num_list) / len(num_list)

averages = list(map(mean, numbers))
print(averages)
```

输出结果：

```
[57.0, 58.2, 50.6, 27.2]
```

将代码改为：

```
numbers = [
              [34, 63, 88, 71, 29],
              [90, 78, 51, 27, 45],
              [63, 37, 85, 46, 22],
              [51, 22, 34, 11, 18]
           ]

# def mean(num_list):
#     return sum(num_list) / len(num_list)
mean = lambda num_list : sum(num_list) / len(num_list)
averages = list(map(mean, numbers))
print(averages)
```

输出结果：

```
[57.0, 58.2, 50.6, 27.2]
```

输出结果是一样的，说明已经正确。



# 练习：Lambda 与 Filter

`filter()` 是一个高阶内置函数，接受函数和可迭代对象作为输入，并返回一个由可迭代对象中的特定元素（该函数针对该元素会返回 True）组成的迭代器。下面的代码使用 `filter()` 从 `cities` 中获取长度少于 10 个字符的名称以创建列表 `short_cities`。测试运行这段代码，看看结果如何。

通过将 `is_short` 函数替换为在 `filter()` 的调用中定义的 lambda 表达式，重写这段代码，使代码更简练。

```
cities = ["New York City", "Los Angeles", "Chicago", "Mountain View", "Denver", "Boston"]

def is_short(name):
    return len(name) < 10

short_cities = list(filter(is_short, cities))
print(short_cities)
```

输出结果：

```
['Chicago', 'Denver', 'Boston']
```

我更改之后的代码：

```
cities = ["New York City", "Los Angeles", "Chicago", "Mountain View", "Denver", "Boston"]

# def is_short(name):
#     return len(name) < 10
is_short = lambda name : len(name) < 10
short_cities = list(filter(is_short, cities))
print(short_cities)
```

输出结果：

```
['Chicago', 'Denver', 'Boston']
```

输出结果一样，说明修改正确。我们下面在看看答案的做法，答案更简洁。

# 练习解决方案：Lambda 与 Map

```
numbers = [
              [34, 63, 88, 71, 29],
              [90, 78, 51, 27, 45],
              [63, 37, 85, 46, 22],
              [51, 22, 34, 11, 18]
           ]

averages = list(map(lambda x: sum(x) / len(x), numbers))
print(averages)
```

### 输出：

```
[57.0, 58.2, 50.6, 27.2]
```

# 练习解决方案：Lambda 与 Filter

```
cities = ["New York City", "Los Angeles", "Chicago", "Mountain View", "Denver", "Boston"]

short_cities = list(filter(lambda x: len(x) < 10, cities))
print(short_cities)
```

### 输出：

```
['Chicago', 'Denver', 'Boston']
```