# Python绘图问题：Matplotlib中柱状图bar使用

Make a bar plot，绘制柱状图。

**参数：** 
\1. left：x轴的位置序列，一般采用arange函数产生一个序列； 
\2. height：y轴的数值序列，也就是柱形图的高度，一般就是我们需要展示的数据； 
\3. alpha：透明度 
\4. width：为柱形图的宽度，一般这是为0.8即可； 
\5. color或facecolor：柱形图填充的颜色； 
\6. edgecolor：图形边缘颜色 
\7. label：解释每个图像代表的含义 
\8. linewidth or linewidths or lw：边缘or线的宽度

**一个例子：**

```
%matplotlib inline
import numpy as np
from matplotlib import pyplot as plt

plt.figure(figsize=(9,6))
n = 8
X = np.arange(n)+1 #X是1,2,3,4,5,6,7,8,柱的个数
#uniform均匀分布的随机数，normal是正态分布的随机数，0.5-1均匀分布的数，一共有n个
Y1 = np.random.uniform(0.5,1.0,n)
Y2 = np.random.uniform(0.5,1.0,n)
plt.bar(X, Y1, alpha=0.9, width = 0.35, facecolor = 'lightskyblue', edgecolor = 'white', label='one', lw=1)
plt.bar(X+0.35, Y2, alpha=0.9, width = 0.35, facecolor = 'yellowgreen', edgecolor = 'white', label='second', lw=1)
plt.legend(loc="upper left") # label的位置在左上，没有这句会找不到label去哪了12345678910111213
```

**1> 没有** plt.legend(loc=”upper left”)这句的图像 
![这里写图片描述](https://img-blog.csdn.net/20171009224906952?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvbGlhbmd6dW9qaWF5aQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

**2> 有** plt.legend(loc=”upper left”)这句的图像 
![这里写图片描述](https://img-blog.csdn.net/20171009235403334?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvbGlhbmd6dW9qaWF5aQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

区别很明显是不是？^_^