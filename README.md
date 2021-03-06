# Udacity学习仓库

讲师：Juna



### 仓库简要介绍

这个仓库里记录了我的数据挖掘实战冲刺科课程的学习笔记；

### 第一章 python基础

编号为1,2,3,4的文件夹里记录的是Python的基础知识，包括Python的学习背景，学习用处；python的数据结构与算符；python的控制流；python函数式编程；python脚本代码的编写；以及非常多的细节，不但记录着学习python必知必会的基础知识，还记录有编写python的代码良好习惯的记录。相对于其他面向对象语言，控制流中有意思的地方有，zip和Enumerate；还有列表推导式。会令你大开眼界。[加入学习](https://github.com/KingfaLuis/Udacity/tree/master/1_python_foundamention)

### 第二章 数据分析基本库

编号为5,6的文件夹的这一部分是从记录学习python的基本库numpy，pandas，Matplotlib的知识点；主要有numpy，pandas处处一维数组的数据结构，二维数组的数据结构：也就是教你如何理解掌握array,series,Dataframe的方法笔记；还有数据分析过程中经常用到的方法，清理数据的方法，以及非常有趣又强大的函数groupby,query;数据可视化的方法。由浅入深的知识概括。[加入学习](https://github.com/KingfaLuis/Udacity/tree/master/2_python_control%20flow)

### 第三章 数据分析案例

7,8.9,10的文件夹就是在经过前面的学习，经过各种对应的练习训练，理解每个知识点用法的基础上，进一步掌握数据分析库numpy，pandas，可视化库numpy，matplotlib的基础上，开始去学习数据分析的过程，数据分析过程中用到的非常有用的方法；继而通过两个案例运用和学习新的数据分析方法来研究解决案例问题；案例一研究关于葡萄酒化学性质和质量等级的数据集；案例二研究一个具有挑战性的燃料经济性数据集。[加入学习](https://github.com/KingfaLuis/Udacity/tree/master/3_python_function)


### 第四章 数据分析过程：案例研究1

通过研究关于葡萄酒化学性质和质量等级的数据集，

**探究如下问题：**

Q1:哪些化学特性在预测葡萄酒质量方面最为重要：

Q2:是否特定类型的葡萄酒（红葡萄酒和白葡萄酒）的品质更高？

Q3:酒精含量更高的葡萄酒是否获得的评价更高？

Q4:味道更甜（仓唐更多）的葡萄酒是否获得的评价更高？

Q5:什么水平的酸度代表质量高？
[加入学习](https://github.com/KingfaLuis/Udacity/tree/master/8_Data%20analysis%20process_case%201/0_%E6%A1%88%E4%BE%8B%E4%B8%80%E6%95%B4%E7%90%86)



### 第五章 数据分析过程：案例研究2：

通过研究燃料经济性数据集；

探究如下问题：

Q1: 与2008年相比，2018年是否有更多的车型（去重后）使用替代能源？比例增长了多少？

Q2: 各车辆类别（veh_class）在燃料经济性方面的改进（mpg 的增长）是多少？

Q3: SmartWay 车辆的特点是什么？它们是否随时间推移发生了改变？（mpg，温室气体排放量）

Q4: 哪些特征与更好的燃料经济性 (mpg) 相关联？

Q5: 对于 2008 年生产且 2018 年仍在生产中的车型，mpg 有多少改进，哪些车辆的改进最多？

Q6: 对于 2008 年生产且 2018 年仍在生产中的车型，mpg 有多少改进，哪些车辆的改进最多？ 
[加入学习](https://github.com/KingfaLuis/Udacity/tree/master/9_Data%20analysis%20process_case%20two)


## 第六章 SQL入门基础知识

这部分主要包括四部分的知识：
[加入学习]()
### 第七章 基本SQL结构化查询语言

在练习过程中使用开源数据库postGRE；对美国一家专门销售纸张公司Patch&Posey的订单记录进行查询，本门课程使用的数据都是这家公司的数据。
[加入学习]()

### 第八章 SQL Join

前面课程介绍了单张表格的查询，但是数据库中，记录着很多张表格，这个数据库有五张表格；实际工作中我们会经常用到多张的表格；关键点就是要找到主键进行连接表格；然后连接后就可以当做一张新的表格去查询想要的信息；

[加入学习](https://github.com/KingfaLuis/Udacity/tree/master/11_SQL/0_sql_join)


### 第九章 SQL聚合

聚合这一部分，可以说是我之前在学校上课和自学数据库的时候很难有这么深的体会的。对于NULL的理解尤为重要，在数据库中，NULL是一种数据类型，它与零不同，他们表示不存在数据的单元格。where条件中表示NULL用 IS NULL 或 IS NOT NULL。使用COUNT统计NULL的个数；还有常用统计的函数SUM;求最大与最小值MAX和MIN;求平均AVG的使用和练习。GROUP BY是这节课以及这部分笔记的重点。

**第一个重点:GROUP BY**

- GROUP BY 可以在数据子集中用来聚合数据。例如，不同客户，不同区域或不同销售组代表分组。
- SELECT语句中的任何一列如果不在聚合函数中，则必须在GROUP BY条件中。
- GROUP BY始终在WHERE 和ORDER BY之间。
- ORDER BY 用于排序，有点像电子表格软件中的sort。

**第二个重点:HAVING和DATE**

	这节课还有两个重点和难点，就是HAVING和DATE的使用；HAVING 是用于过滤，采用“子查询”的方式来实现。DATE就是用日期的处理，主要记录两个日期函数DATE_TRUNC和DATE_PART这两个函数就足够入门了。阅读以下精彩的博文和文档进入更宽广的

世界。之所以说他们难是要涉及到业务更精细化的逻辑。

- https://blog.modeanalytics.com/date-trunc-sql-timestamp-function-count-on/
- https://www.postgresql.org/docs/9.1/static/functions-datetime.html

**第三个重点:CASE**

- CASE语句时钟位于SELECT条件中。
- CASE必须包含以下几个部分：when,then,end,else是可选组成部分，用来包含符合上述任一CASE条件的情况。
- 可以在when和then之间使用任何条件运算符编写任何条件语句（例如：where）。
- 可以再次包含多个 WHEN 语句以及 ELSE 语句 。

单独列出来是因为我在后面的数据分析项目应用中，对比了pandas的API的groupby和这三个重点部分用法。
[加入学习]()



## 第十章 SQL子查询和临时表格

子查询这部分是高级功能；主要是高级功能子查询和公用表达式with语句。称为数据分析师，你一定会爱上子查询和with语句的。详细多练习笔记中的题目。就像打羽毛球，多练点高级技术动作，练念不忘，必有回响！
[加入学习]()



## 第十一章 SQL数据清理

这节课学习了多个高级技能：

1. 清理和重新整理混乱的数据。
2. 将列转换为不同的数据类型。
3. 处理NULL的技巧。

- LEFT
- RIGHT
- LENGTH
- POSITION
- STRPOS
- LOWER
- UPPER
- CAST
- COALESCE

**注意**: 注意每个文件的开头部分的序号的理解：文件名开头的序号，是为了和我学的课时对应，
很多标题都把几个数字使用‘&’符号连接起来，是为了表示这是几个课时的课程的笔记结合，是因为有的几个课时讲的是同一个内容。
这样以后我再次复习视屏课程的时候，就会很清楚对应是哪个课程。希望读者们能清楚。

