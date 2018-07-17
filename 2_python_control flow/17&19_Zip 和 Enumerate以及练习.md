# Zip 和 Enumerate

`zip` 和 `enumerate` 是实用的内置函数，可以在处理循环时用到。

### Zip

`zip` 返回一个将多个可迭代对象组合成一个元组序列的迭代器。每个元组都包含所有可迭代对象中该位置的元素。例如，

`list(zip(['a', 'b', 'c'], [1, 2, 3]))` 将输出 `[('a', 1), ('b', 2), ('c', 3)]`.

正如 `range()` 一样，我们需要将其转换为列表或使用循环进行遍历以查看其中的元素。

你可以如下所示地用 `for` 循环拆封每个元组。

```
letters = ['a', 'b', 'c']
nums = [1, 2, 3]

for letter, num in zip(letters, nums):
    print("{}: {}".format(letter, num))
```

除了可以将两个列表组合到一起之外，还可以使用星号拆封列表。

```
some_list = [('a', 1), ('b', 2), ('c', 3)]
letters, nums = zip(*some_list)
```

这样可以创建正如之前看到的相同 `letters` 和 `nums` 列表。

### Enumerate

`enumerate` 是一个会返回元组迭代器的内置函数，这些元组包含列表的索引和值。当你需要在循环中获取可迭代对象的每个元素及其索引时，将经常用到该函数。

```
letters = ['a', 'b', 'c', 'd', 'e']
for i, letter in enumerate(letters):
    print(i, letter)
```

这段代码将输出：

```
0 a
1 b
2 c
3 d
4 e
```



练习：Zip 和 Enumerate

# 练习：组合坐标

使用 `zip` 写一个 `for` 循环，该循环会创建一个字符串，指定每个点的标签和坐标，并将其附加到列表 `points`。每个字符串的格式应该为 `label: x, y, z`。例如，第一个坐标的字符串应该为 `F: 23, 677, 4`。

```
x_coord = [23, 53, 2, -12, 95, 103, 14, -5]
y_coord = [677, 233, 405, 433, 905, 376, 432, 445]
z_coord = [4, 16, -6, -42, 3, -6, 23, -1]
labels = ["F", "J", "A", "Q", "Y", "B", "W", "X"]

points = []
# write your for loop here
labels_xyz = zip(labels, x_coord, y_coord, z_coord)
for point in labels_xyz:
    points.append("{}: {}, {}, {}".format(*point))

for point in points:
    print(point)
```

输出结果：

```
F: 23, 677, 4
J: 53, 233, 16
A: 2, 405, -6
Q: -12, 433, -42
Y: 95, 905, 3
B: 103, 376, -6
W: 14, 432, 23
X: -5, 445, -1
```

# 练习：将列表组合成字典

使用 `zip` 创建一个字典 `cast`，该字典使用 `names` 作为键，并使用 `heights` 作为值。

```
cast_names = ["Barney", "Robin", "Ted", "Lily", "Marshall"]
cast_heights = [72, 68, 72, 66, 76]

cast = dict(zip(cast_names,cast_heights)) # replace with your code
print(cast)
```

输出结果：结果顺序可能不一样，因为字典是无序的。

```
{'Barney': 72, 'Marshall': 76, 'Robin': 68, 'Ted': 72, 'Lily': 66}
```

# 练习：拆封元组

将 `cast` 元组拆封成两个 `names` 和 `heights` 元组。

```
cast = (("Barney", 72), ("Robin", 68), ("Ted", 72), ("Lily", 66), ("Marshall", 76))

# define names and heights here
names,heights = zip(*cast)

print(names)
print(heights)
```

输出结果：

```
('Barney', 'Robin', 'Ted', 'Lily', 'Marshall')
(72, 68, 72, 66, 76)
```

# 练习：用 Zip 进行转置

使用 `zip` 将 `data` 从 4x3 矩阵转置成 3x4 矩阵。实际上有一个很酷的技巧。如果想不出答案的话，可以查看解决方案。

```

```



```
data = ((0, 1, 2), (3, 4, 5), (6, 7, 8), (9, 10, 11))

data_transpose =tuple(zip(*data)) # replace with your code
print(data_transpose)
```

输出结果：

```
((0, 3, 6, 9), (1, 4, 7, 10), (2, 5, 8, 11))
```

这个技巧有必要去记住，

# 练习：Enumerate

使用 `enumerate` 修改列表 `cast`，使每个元素都包含姓名，然后是角色的对应身高。例如，`cast` 的第一个元素应该从 `"Barney Stinson"` 更改为 `"Barney Stinson 72”`。

```
cast = ["Barney Stinson", "Robin Scherbatsky", "Ted Mosby", "Lily Aldrin", "Marshall Eriksen"]
heights = [72, 68, 72, 66, 76]

# write your for loop here
for i,chracter in enumerate(cast):
    cast[i] = chracter + " " + str(heights[i])
    

print(cast)
```

输出结果：

```
['Barney Stinson 72', 'Robin Scherbatsky 68', 'Ted Mosby 72', 'Lily Aldrin 66', 'Marshall Eriksen 76']
```



# 练习解决方案：组合坐标

```
x_coord = [23, 53, 2, -12, 95, 103, 14, -5]
y_coord = [677, 233, 405, 433, 905, 376, 432, 445]
z_coord = [4, 16, -6, -42, 3, -6, 23, -1]
labels = ["F", "J", "A", "Q", "Y", "B", "W", "X"]

points = []
for point in zip(labels, x_coord, y_coord, z_coord):
    points.append("{}: {}, {}, {}".format(*point))

for point in points:
    print(point)
```

### 输出：

```
F: 23, 677, 4
J: 53, 233, 16
A: 2, 405, -6
Q: -12, 433, -42
Y: 95, 905, 3
B: 103, 376, -6
W: 14, 432, 23
X: -5, 445, -1
```

注意，元组在 `format` 方法中使用 `*` 进行了拆封。这样可以使代码更整洁！

# 练习解决方案：将列表组合成字典

```
cast_names = ["Barney", "Robin", "Ted", "Lily", "Marshall"]
cast_heights = [72, 68, 72, 66, 76]

cast = dict(zip(cast_names, cast_heights))
print(cast)
```

### 输出:

该输出中的元素顺序可能有变化，因为字典是无序的。

```
{'Lily': 66, 'Barney': 72, 'Marshall': 76, 'Ted': 72, 'Robin': 68}
```

# 练习解决方案：拆封元组

```
cast = (("Barney", 72), ("Robin", 68), ("Ted", 72), ("Lily", 66), ("Marshall", 76))

names, heights = zip(*cast)
print(names)
print(heights)
```

### 输出：

```
('Barney', 'Robin', 'Ted', 'Lily', 'Marshall')
(72, 68, 72, 66, 76)
```

# 练习解决方案：用 Zip 进行转置

```
data = ((0, 1, 2), (3, 4, 5), (6, 7, 8), (9, 10, 11))

data_transpose = tuple(zip(*data))
print(data_transpose)
```

### 输出：

```
((0, 3, 6, 9), (1, 4, 7, 10), (2, 5, 8, 11))
```

**这是一个很实用的技巧，有必要了解一下**！

# 练习解决方案：Enumerate

```
cast = ["Barney Stinson", "Robin Scherbatsky", "Ted Mosby", "Lily Aldrin", "Marshall Eriksen"]
heights = [72, 68, 72, 66, 76]

for i, character in enumerate(cast):
    cast[i] = character + " " + str(heights[i])

print(cast)
```

### 输出：

```
['Barney Stinson 72', 'Robin Scherbatsky 68', 'Ted Mosby 72', 'Lily Aldrin 66', 'Marshall Eriksen 76']
```
