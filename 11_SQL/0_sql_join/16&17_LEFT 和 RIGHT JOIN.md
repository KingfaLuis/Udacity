# LEFT 和 RIGHT JOIN

### 习题 1/4

选择以下所有表述正确的语句。

- [x] 如果我们更改 **FROM** 和 **JOIN** 语句中的表格，则 **LEFT JOIN** 和 **RIGHT JOIN** 的结果一样。
- [x] **LEFT JOIN** 将**至少**返回所有 **INNER JOIN** 返回的所有行。
- [x] **JOIN** 和 **INNER JOIN** 是一样的。
- [x] **LEFT OUTER JOIN** 和 **LEFT JOIN** 是一样的。

[![img](https://s3.cn-north-1.amazonaws.com.cn/u-img/048f2da8-95b8-4c76-b553-57533a796bf0)](https://classroom.udacity.com/nanodegrees/nd678-cn-1/parts/81cd15b3-bd19-459e-a223-7309e4fc53eb/modules/b47f298e-dc95-4791-8315-12836c86ef31/lessons/8f23fc69-7c88-4a94-97a4-d5f6ef51cf7b/concepts/b84358f0-5156-41c2-9497-2a45a7f36035#)

以上是两个小的表格，用来检测下你的 **JOIN** 知识。你可以点击图片，看的更清楚。

**Country** 有 6 行和 2 列：

- **countryid** 和 **countryName**

**State** 有 6 行和 3 列：

- **stateid**、**countryid** 和 **stateName**

根据上述表格判断以下问题的答案。

### 习题 2/4

将每个语句与所描述的项相匹配。

State.stateName

Country.countryName

| 描述                       | 项                |
| -------------------------- | ----------------- |
| **Country** 表格的主键     | Country.countryid |
| **State** 表格的主键。     | State.stateid     |
| 在连接表格时会用到的外键。 | State.countryid   |

[![img](https://s3.cn-north-1.amazonaws.com.cn/u-img/6abba5d4-2a22-4eec-9448-f27b2b78dfef)](https://classroom.udacity.com/nanodegrees/nd678-cn-1/parts/81cd15b3-bd19-459e-a223-7309e4fc53eb/modules/b47f298e-dc95-4791-8315-12836c86ef31/lessons/8f23fc69-7c88-4a94-97a4-d5f6ef51cf7b/concepts/b84358f0-5156-41c2-9497-2a45a7f36035#)

上面的两个表格只是为了避免滚动幅度太大，如果你要执行以下查询：

```sql
SELECT c.countryid, c.countryName, s.stateName
FROM Country c
JOIN State s
ON c.countryid = s.countryid;
```

### 习题 3/4

将查询结果与说明相匹配。

| 描述                                       | 结果 |
| ------------------------------------------ | ---- |
| 生成的表格中的列数。                       | 3    |
| 生成的表格中的行数。                       | 6    |
| countryid `1` 将在生成的表格中出现的次数。 | 2    |
| countryid `6` 将在生成的表格中出现的次数。 | 0    |

因为这是 **JOIN**（实际上是 **INNER JOIN**），我们只能获得在两个表格中都出现了的行。因此，生成的表格将看起来像右侧表格，并获取列 **countryName**。因为1、2、3 和 4 是两个表格中的 **countryid**，因此将同时获取这些信息。**countryid** 5 和 6 仅出现在了 **Country** 表格中，因此将忽略这两行。 

[![img](https://s3.cn-north-1.amazonaws.com.cn/u-img/a78d3931-3430-4acc-8cda-daa7fbd12730)](https://classroom.udacity.com/nanodegrees/nd678-cn-1/parts/81cd15b3-bd19-459e-a223-7309e4fc53eb/modules/b47f298e-dc95-4791-8315-12836c86ef31/lessons/8f23fc69-7c88-4a94-97a4-d5f6ef51cf7b/concepts/b84358f0-5156-41c2-9497-2a45a7f36035#)

上面的两个表格同样只是为了避免滚动幅度太大，如果你要执行以下查询：

```sql
SELECT c.countryid, c.countryName, s.stateName
FROM Country c
LEFT JOIN State s
ON c.countryid = s.countryid;
```

### 习题 4/4

将查询结果与说明相匹配

| 描述                                       | 结果 |
| ------------------------------------------ | ---- |
| 生成的表格中的列数。                       | 3    |
| 生成的表格中的行数。                       | 8    |
| countryid `1` 将在生成的表格中出现的次数。 | 2    |
| countryid `6` 将在生成的表格中出现的次数。 | 1    |



# LEFT JOIN 和 RIGHT JOIN 解决方案

这一部分讲解的是上一部分的最后两个问题，首先再看看我们处理的这两个表格：

[![img](https://s3.cn-north-1.amazonaws.com.cn/u-img/441c4486-fa15-4726-86dd-a2d78f286f4f)](https://classroom.udacity.com/nanodegrees/nd678-cn-1/parts/81cd15b3-bd19-459e-a223-7309e4fc53eb/modules/b47f298e-dc95-4791-8315-12836c86ef31/lessons/8f23fc69-7c88-4a94-97a4-d5f6ef51cf7b/concepts/d57c222e-1ac5-43d4-8685-e3365f200735#)

### INNER JOIN 问题

这些问题旨在让你对 **LEFT JOIN** 和 **INNER JOIN** 的原理有所了解，然后才能使用它们处理更复杂的问题。

对于如下所示的 **INNER JOIN**：

```
SELECT c.countryid, c.countryName, s.stateName
FROM Country c
JOIN State s
ON c.countryid = s.countryid;
```

我们实际上是将两个表格中匹配的主键和外键行连接到一起，如下图所示。

[![img](https://s3.cn-north-1.amazonaws.com.cn/u-img/5d63b6f0-35ac-4570-bcde-fc39fc802e36)](https://classroom.udacity.com/nanodegrees/nd678-cn-1/parts/81cd15b3-bd19-459e-a223-7309e4fc53eb/modules/b47f298e-dc95-4791-8315-12836c86ef31/lessons/8f23fc69-7c88-4a94-97a4-d5f6ef51cf7b/concepts/d57c222e-1ac5-43d4-8685-e3365f200735#)

生成的表格将如下所示：

| **countryid** | **countryName** | **stateName** |
| ------------- | --------------- | ------------- |
| 1             | India           | Maharashtra   |
| 1             | India           | Punjab        |
| 2             | Nepal           | Kathmandu     |
| 3             | United States   | California    |
| 3             | United States   | Texas         |
| 4             | Canada          | Alberta       |

### LEFT JOIN 问题

这些问题旨在让你对 **LEFT JOIN** 和 **INNER JOIN** 的原理有所了解，然后才能使用它们处理更复杂的问题。

对于如下所示的 **LEFT JOIN**：

```
SELECT c.countryid, c.countryName, s.stateName
FROM Country c
LEFT JOIN State s
ON c.countryid = s.countryid;
```

和之前一样，我们实际上是将两个表格中匹配的主键和外键行连接到一起，但是我们还从 **Country** 表格中获取额外的行，即使它们在 **State** 表格中没有匹配的项。因此，我们获取的是 **INNER JOIN** 生成的所有行，同时还获取 **FROM** 中的表格里的其他行。

[![img](https://s3.cn-north-1.amazonaws.com.cn/u-img/825e60d9-7ed3-4ab5-baa2-23018ab15920)](https://classroom.udacity.com/nanodegrees/nd678-cn-1/parts/81cd15b3-bd19-459e-a223-7309e4fc53eb/modules/b47f298e-dc95-4791-8315-12836c86ef31/lessons/8f23fc69-7c88-4a94-97a4-d5f6ef51cf7b/concepts/d57c222e-1ac5-43d4-8685-e3365f200735#)

生成的表格将如下所示：

| **countryid** | **countryName** | **stateName** |
| ------------- | --------------- | ------------- |
| 1             | India           | Maharashtra   |
| 1             | India           | Punjab        |
| 2             | Nepal           | Kathmandu     |
| 3             | United States   | California    |
| 3             | United States   | Texas         |
| 4             | Canada          | Alberta       |
| 5             | Sri Lanka       | NULL          |
| 6             | Brazil          | NULL          |

### 最后的 LEFT JOIN 注意事项

如果我们翻转表格顺序的话，实际上和 **JOIN** 语句获得的结果完全一样：

```
SELECT c.countryid, c.countryName, s.stateName
FROM State s
LEFT JOIN Country c
ON c.countryid = s.countryid;
```

这是因为如果 **State** 位于**左侧**表格中，则所有行再次出现在**右侧**表格中。

[![img](https://s3.cn-north-1.amazonaws.com.cn/u-img/d84ccaec-ff2c-44b2-97da-80b5ea47a069)](https://classroom.udacity.com/nanodegrees/nd678-cn-1/parts/81cd15b3-bd19-459e-a223-7309e4fc53eb/modules/b47f298e-dc95-4791-8315-12836c86ef31/lessons/8f23fc69-7c88-4a94-97a4-d5f6ef51cf7b/concepts/d57c222e-1ac5-43d4-8685-e3365f200735#)

生成的表格将如下所示：

| **countryid** | **countryName** | **stateName** |
| ------------- | --------------- | ------------- |
| 1             | India           | Maharashtra   |
| 1             | India           | Punjab        |
| 2             | Nepal           | Kathmandu     |
| 3             | United States   | California    |
| 3             | United States   | Texas         |
| 4             | Canada          | Alberta       |

