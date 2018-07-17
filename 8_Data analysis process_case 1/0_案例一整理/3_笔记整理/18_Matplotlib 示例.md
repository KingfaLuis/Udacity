# 18_Matplotlib 示例

以下是使用 Matplotlib 创建的类型和质量图。正如你所看到的，Matplotlib 可以让我们对可视化操作有更多的可控性。

[![img](https://s3.cn-north-1.amazonaws.com.cn/u-img/7a0e4652-0ccf-4cd2-9f42-d39cd76ff22d)](https://classroom.udacity.com/nanodegrees/nd678-cn-1/parts/2ec9632a-9e67-4614-992d-2d0b8552a02d/modules/aba991e6-3f55-4025-81ab-08932ec5f46f/lessons/77286f5a-b206-4807-aaa0-7ecfc690268e/concepts/feed3f58-82ea-40c3-a3a5-3ac88fc4be58#)

在开始此图的绘制之前，我们来看使用 Matplotlib 创建条形图的一个简单示例。我们可以使用 pyplot 的 [bar](https://matplotlib.org/api/pyplot_api.html#matplotlib.pyplot.bar) 函数。

提示：不同页面上的workspace是不相连接的。为了保证代码的正常运行，有时候需要同学们点击左上角的jupyter按钮，将上一个workspace中的数据下载，并上传upload到另外的workspace中。

# 用 Matplotlib 创建柱状图

```python
import matplotlib.pyplot as plt
% matplotlib inline
```

pyplot 的 `bar` 功能中有两个必要参数：条柱的 x 坐标和条柱的高度。

```python
plt.bar([1, 2, 3], [224, 620, 425]);
```

![png](../../0_%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E6%A1%88%E4%BE%8B%E4%B8%8E%E5%AE%9E%E6%88%98%E9%A1%B9%E7%9B%AE/1_%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E8%BF%87%E7%A8%8B_%E6%A1%88%E4%BE%8B%E7%A0%94%E7%A9%B6%E4%B8%80/18_%E7%A4%BA%E4%BE%8Bmatplotlib_example-zh/output_3_0.png)

可以利用 pyplot 的 `xticks` 功能，或通过在 `bar` 功能中指定另一个参数，指定 x 轴刻度标签。以下两个框的结果相同。

```python
# 绘制条柱
plt.bar([1, 2, 3], [224, 620, 425])

# 为 x 轴指定刻度标签及其标签
plt.xticks([1, 2, 3], ['a', 'b', 'c']);
```

![png](../../0_%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E6%A1%88%E4%BE%8B%E4%B8%8E%E5%AE%9E%E6%88%98%E9%A1%B9%E7%9B%AE/1_%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E8%BF%87%E7%A8%8B_%E6%A1%88%E4%BE%8B%E7%A0%94%E7%A9%B6%E4%B8%80/18_%E7%A4%BA%E4%BE%8Bmatplotlib_example-zh/output_5_0.png)



```python
# 用 x 轴的刻度标签绘制条柱
plt.bar([1, 2, 3], [224, 620, 425], tick_label=['a', 'b', 'c']);
```

![png](../../0_%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E6%A1%88%E4%BE%8B%E4%B8%8E%E5%AE%9E%E6%88%98%E9%A1%B9%E7%9B%AE/1_%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90%E8%BF%87%E7%A8%8B_%E6%A1%88%E4%BE%8B%E7%A0%94%E7%A9%B6%E4%B8%80/18_%E7%A4%BA%E4%BE%8Bmatplotlib_example-zh/output_6_0.png)

用以下方法设置轴标题和标签。

```python
plt.bar([1, 2, 3], [224, 620, 425], tick_label=['a', 'b', 'c'])
plt.title('Some Title')
plt.xlabel('Some X Label')
plt.ylabel('Some Y Label');
```