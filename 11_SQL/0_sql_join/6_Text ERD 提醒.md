# Text: ERD 提醒

# 实体关系图

你可能还记得，在上节课，我们提到**实体关系图** (ERD) 是查看数据库中数据的常见方式。它也是了解如何从多个表格中获取数据的关键要素。

如果能知道 Parch & Posey handy 的 RED 看起来怎样，会比较有帮助，因此我在下面再次提供了该图。**你甚至可以打印一份，这样在完成剩下的练习时可以参考。**

[![img](https://s3.cn-north-1.amazonaws.com.cn/u-img/dac4dd37-f8c7-4249-9c64-cb9716022ed3)](https://classroom.udacity.com/nanodegrees/nd678-cn-1/parts/81cd15b3-bd19-459e-a223-7309e4fc53eb/modules/b47f298e-dc95-4791-8315-12836c86ef31/lessons/8f23fc69-7c88-4a94-97a4-d5f6ef51cf7b/concepts/57f82755-506c-4fb5-af0f-312b52ed340e#)

# 表格与列

在 Parch & Posey 数据库中，有 5 个表格

1. **web_events**
2. **accounts**
3. **orders**
4. **sales_reps**
5. **region**

你将发现，表格中某些列的列名称旁边具有 **PK** 或 **FK**，而其他列根本没有标签。

如果你再仔细观察，可能会发现，**PK** 在每个表格中与第一列相关。**PK** 表示**主键**。**每个表格都存在主键，它是每行的值都唯一的列。**

如果你查看我们的数据库中每个表格的前几行，你会发现这个首个 **PK** 列始终是唯一的。对于此数据库，它始终称为 `id`，但并非所有数据库都这样。



```sql
select *
from accounts
limit 5;


```



![1530859847244](C:\Users\ADMINI~1\AppData\Local\Temp\1530859847244.png)



```sql
select *
from orders
limit 5;
```



![1530859889838](C:\Users\ADMINI~1\AppData\Local\Temp\1530859889838.png)



```sql
select *
from region
limit 5;
```



![1530859942231](C:\Users\ADMINI~1\AppData\Local\Temp\1530859942231.png)



```sql
select *
from sales_reps
limit 5;
```



![1530860047551](C:\Users\ADMINI~1\AppData\Local\Temp\1530860047551.png)



```sql
select *
from web_events
limit 5;
```



![1530860144592](C:\Users\ADMINI~1\AppData\Local\Temp\1530860144592.png)