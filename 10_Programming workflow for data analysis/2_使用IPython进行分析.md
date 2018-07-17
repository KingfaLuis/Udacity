# 关于 IPython

[IPython](http.s://ipython.org/) 提供了我们在 Jupyter Notebook 中使用的交互式 Python 内核。事实上，我们可以在 Jupyter Notebook 之外，通过我们终端上的命令行界面使用 IPython。这对于快速修改、探索、实验，甚至是运行 Python 脚本来说都非常方便，真的很棒！

你可以[在此](http://jupyter.readthedocs.io/en/latest/architecture/how_jupyter_ipython_work.html) 阅读有关 IPython 和 Jupyter Notebook 工作原理的更多信息。你也可以[在此](http://ipython.readthedocs.io/en/stable/) 找到官方 IPython 文档。

要使用 IPython 的命令行界面，只需在终端键入 `ipython` 即可。如果你已经安装了 Jupyter Notebook ，这应该可以工作。像我们一直在 Jupyter Notebook 中一样，我们会先导入包并加载数据集。

[![img](https://s3.cn-north-1.amazonaws.com.cn/u-img/b81593b9-9bce-4194-a042-7ce6f406fd4f)](https://classroom.udacity.com/nanodegrees/nd678-cn-1/parts/2ec9632a-9e67-4614-992d-2d0b8552a02d/modules/aba991e6-3f55-4025-81ab-08932ec5f46f/lessons/a346dcfb-58cd-43ec-b786-fec1022155f0/concepts/35b42164-ba00-4d0b-aa32-bc96d65c3997#)

即使在终端，我们仍然可以使用 `head` 以相同的方式查看数据集。

[![img](https://s3.cn-north-1.amazonaws.com.cn/u-img/6ba56bfa-1734-49d9-8eb3-317116bc210a)](https://classroom.udacity.com/nanodegrees/nd678-cn-1/parts/2ec9632a-9e67-4614-992d-2d0b8552a02d/modules/aba991e6-3f55-4025-81ab-08932ec5f46f/lessons/a346dcfb-58cd-43ec-b786-fec1022155f0/concepts/35b42164-ba00-4d0b-aa32-bc96d65c3997#)

即使在 IPython 中，你仍然可以使用命令行命令！所以我们可以执行一些操作，比如检查我们的目录，以查找其他文件并重命名它们。

[![img](https://s3.cn-north-1.amazonaws.com.cn/u-img/4fa62fa7-6336-4dfb-8e57-244b85f1d5a6)](https://classroom.udacity.com/nanodegrees/nd678-cn-1/parts/2ec9632a-9e67-4614-992d-2d0b8552a02d/modules/aba991e6-3f55-4025-81ab-08932ec5f46f/lessons/a346dcfb-58cd-43ec-b786-fec1022155f0/concepts/35b42164-ba00-4d0b-aa32-bc96d65c3997#)

在终端使用 IPython 非常便于快速更改文件。例如，你可能想在发送 csv 文件之前更改数据集中的列名称。

[![img](https://s3.cn-north-1.amazonaws.com.cn/u-img/4c0ea7df-19a4-4738-addb-0c5af91ea383)](https://classroom.udacity.com/nanodegrees/nd678-cn-1/parts/2ec9632a-9e67-4614-992d-2d0b8552a02d/modules/aba991e6-3f55-4025-81ab-08932ec5f46f/lessons/a346dcfb-58cd-43ec-b786-fec1022155f0/concepts/35b42164-ba00-4d0b-aa32-bc96d65c3997#)

这里的可视化也是一样的，除了没有 `% matplotlib inline`，因为这是特定于 Jupyter notebook 的。要显示我们的可视化，我们需要调用 `plt.show()`.

[![img](https://s3.cn-north-1.amazonaws.com.cn/u-img/5c58bf37-7f06-4074-8cc2-e3024e696f6e)](https://classroom.udacity.com/nanodegrees/nd678-cn-1/parts/2ec9632a-9e67-4614-992d-2d0b8552a02d/modules/aba991e6-3f55-4025-81ab-08932ec5f46f/lessons/a346dcfb-58cd-43ec-b786-fec1022155f0/concepts/35b42164-ba00-4d0b-aa32-bc96d65c3997#)

输入它将像这样在另一个窗口中打开此图。

[![img](https://s3.cn-north-1.amazonaws.com.cn/u-img/4a7810eb-0e81-4f04-ad6e-3fbdca680e95)](https://classroom.udacity.com/nanodegrees/nd678-cn-1/parts/2ec9632a-9e67-4614-992d-2d0b8552a02d/modules/aba991e6-3f55-4025-81ab-08932ec5f46f/lessons/a346dcfb-58cd-43ec-b786-fec1022155f0/concepts/35b42164-ba00-4d0b-aa32-bc96d65c3997#)

我经常在 IPython 中做的一件事，是练习或实验不同的函数、算法或 Python。有时候，我甚至快速查看这里，以便在阅读文档之前记住函数的工作原理（虽然阅读文档也是一个非常好的了解函数的方法！）

[![img](https://s3.cn-north-1.amazonaws.com.cn/u-img/cfbd091b-b923-466d-97a1-e4d01f73814e)](https://classroom.udacity.com/nanodegrees/nd678-cn-1/parts/2ec9632a-9e67-4614-992d-2d0b8552a02d/modules/aba991e6-3f55-4025-81ab-08932ec5f46f/lessons/a346dcfb-58cd-43ec-b786-fec1022155f0/concepts/35b42164-ba00-4d0b-aa32-bc96d65c3997#)

这只是一个简单概述，让你认识使用新 Python 练习数据分析技能的不同工具。如果你想了解更多信息，请务必查看上面链接的文档！