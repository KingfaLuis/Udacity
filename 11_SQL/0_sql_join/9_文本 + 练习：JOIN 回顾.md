# 文本 + 练习：JOIN 回顾

# JOIN 回顾

我们回顾下你编写的第一个 JOIN 语句。

```sql
SELECT orders.*
FROM orders
JOIN accounts
ON orders.account_id = accounts.id;
```

以下是这两个表格的 ERD：

[![img](https://s3.cn-north-1.amazonaws.com.cn/u-img/f25048f0-3208-4eb6-a176-f92a8b177c2d)](https://classroom.udacity.com/nanodegrees/nd678-cn-1/parts/81cd15b3-bd19-459e-a223-7309e4fc53eb/modules/b47f298e-dc95-4791-8315-12836c86ef31/lessons/8f23fc69-7c88-4a94-97a4-d5f6ef51cf7b/concepts/6bcadea2-78dd-4aa5-a9f1-f84be429067b#)

# 注意

注意，我们的 SQL 查询包含两个想要连接的表格：一个来自 **FROM**，另一个来自 **JOIN**。然后在 **ON** 中，我们**始终**让**主键**等于**外键**：

我们按照以下方式连接任何两个表格。

[![img](https://s3.cn-north-1.amazonaws.com.cn/u-img/0376b35a-d33c-44a7-b6a0-436ea7be9509)](https://classroom.udacity.com/nanodegrees/nd678-cn-1/parts/81cd15b3-bd19-459e-a223-7309e4fc53eb/modules/b47f298e-dc95-4791-8315-12836c86ef31/lessons/8f23fc69-7c88-4a94-97a4-d5f6ef51cf7b/concepts/6bcadea2-78dd-4aa5-a9f1-f84be429067b#)

### 练习题

# 练习

参考以上图片。如果我们想连接 `sales_reps` 和 `region` 表格，如何操作？

- [ ] ON sales_reps.id = region.id
- [ ] ON sales_reps.id = region.name
- [x] ON sales_reps.region_id = region.id
- [ ] ON region.id = sales_reps.id

在这个语句中，表格名称的顺序并不重要。因此，也可以写成 `ON region.id = sales_reps.region_id` 

# 连接多个表格

可以利用同一逻辑连接多个表格。看看下面的三个表格。

[![img](https://s3.cn-north-1.amazonaws.com.cn/u-img/90e0b63f-a6f0-473b-8225-091696c95cf4)](https://classroom.udacity.com/nanodegrees/nd678-cn-1/parts/81cd15b3-bd19-459e-a223-7309e4fc53eb/modules/b47f298e-dc95-4791-8315-12836c86ef31/lessons/8f23fc69-7c88-4a94-97a4-d5f6ef51cf7b/concepts/6bcadea2-78dd-4aa5-a9f1-f84be429067b#)

# 代码

如果我们想连接所有这三个表格，我们可以采用相同的逻辑。

```sql
FROM web_events
JOIN accounts
ON web_events.account_id = accounts.id
JOIN orders
ON accounts.id = orders.account_id
```

现在，我们的 **SELECT** 语句可以从所有三个表格中获取数据。同样，**JOIN** 存储的是表格，**ON** 是让**主键**等于**外键**。

**SELECT** 语句将需要指定你想从中获取列的表格：

```sql
SELECT web_events.channel, accounts.name, orders.total
```

我们可以继续按照这一流程操作，连接所有要连接的表格。为了提高效率，我们可能不希望这么做，除非需要从所有表格中获取信息。