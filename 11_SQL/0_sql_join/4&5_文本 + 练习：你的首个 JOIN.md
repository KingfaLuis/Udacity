---
typora-root-url: D:\lyfFolder\Mysql笔记\0_sql_udacity\0_sql_join
---

# 文本 + 练习：你的首个 JOIN

# 编写你的首个 JOIN

以下是一个 **JOIN** 语句，你将有很多实践机会，没有什么学习方法比实践更强了。你将发现，我们在普通查询中引入了两个新的部分：**JOIN** 和 **ON**。**JOIN** 指定了你要从中获取数据的第二个表格。**ON** 表示你想如何合并 **FROM**和 **JOIN** 语句中的表格。

```sql
SELECT orders.*
FROM orders
JOIN accounts
ON orders.account_id = accounts.id;
```

尝试自己运行下面的查询。

![1530858613436](C:\Users\ADMINI~1\AppData\Local\Temp\1530858613436.png)



### 要注意什么

我们能够从两个表格中获取数据：

1. **orders**
2. **accounts**

我们仅从 **orders** 表格中获取数据。

**ON** 语句存储的是两个表格中相连的两列。下个部分将重点讲解这一概念。

### 练习问题

1. 尝试获取 **accounts** 表格中的所有数据，以及 **orders** 表格中的所有数据。
2. 尝试从 **orders** 表格中获取 **standard_qty**、**gloss_qty** 和 **poster_qty**，并从 **accounts** 表格中获取 **website** 和 **primary_poc**。

以下是练习这两个问题的另一个数据集，你可以在下个部分检查你的答案。

1.尝试获取 **accounts** 表格中的所有数据，以及 **orders** 表格中的所有数据。

```sql
SELECT orders.*, accounts.*
FROM accounts
JOIN orders
ON accounts.id = orders.account_id;#通过主键链接


```

输出结果：

![1530859503823](/C:/Users/ADMINI~1/AppData/Local/Temp/1530859503823.png)

2.尝试从 **orders** 表格中获取 **standard_qty**、**gloss_qty** 和 **poster_qty**，并从 **accounts** 表格中获取 **website** 和 **primary_poc**。

```sql
select standard_qty,gloss_qty,poster_qty,website,primary_poc
from orders
join accounts
on accounts.id = orders.account_id;
```



输出结果：

![1530859341739](/C:/Users/ADMINI~1/AppData/Local/Temp/1530859341739.png)

### 解决方案

1.

```sql
SELECT orders.*, accounts.*
FROM accounts
JOIN orders
ON accounts.id = orders.account_id;
```

注意，上述结果与你切换 **FROM** 和 **JOIN** 中的表格得到的结果一样。此外，`=` 两边的列顺序并不重要。

2.

```sql
SELECT orders.standard_qty, orders.gloss_qty,
orders.poster_qty,  accounts.website,
accounts.primary_poc
FROM orders
JOIN accounts
ON orders.account_id = accounts.id
```

注意，我们需要在 **SELECT** 语句中指定某列所来自的每个表格。