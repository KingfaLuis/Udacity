# 文本：其他 JOIN 注意事项

# JOIN 简介

### INNER JOIN

注意，到目前为止介绍的**每个** JOIN 都是 **INNER JOIN**，即我们仅获取在两个表格中都匹配存在的行。

新的 **JOIN** 使我们能够获取可能仅在其中一个表格中存在的行。这就会导致一种新的数据类型，叫做 **NULL**。我们将在下节课详细讲解这一数据类型。

### 注意

你可能见过以下 SQL 语法

```sql
LEFT OUTER JOIN
```

或

```sql
RIGHT OUTER JOIN
```

这些命令和我们在上个视频中学过的 **LEFT JOIN** 和 **RIGHT JOIN** 完全一样。

### OUTER JOIN

最后一种连接类型是外连接，它将返回内连接的结果，以及被连接的表格中没有匹配的行。

这种连接返回的是与两个表格中的某个表格不匹配的行，完整的外连接用例**非常罕见**。

你可以在[此处](http://www.w3resource.com/sql/joins/perform-a-full-outer-join.php)查看外连接示例，并在[此处](https://stackoverflow.com/questions/2094793/when-is-a-good-situation-to-use-a-full-outer-join)查看罕见使用情况说明。由于这种连接的使用情况很少见，因此我们将不消费时间讨论了。

和上面的相似，你可能还会看到 **FULL OUTER JOIN**，它和 **OUTER JOIN** 一样。