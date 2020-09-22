---
title: 从R中调用Python
author: ''
date: '2020-09-21'
slug: r,python
categories:
  - R; Python
tags:
  - R; Python
---

最近开始遥感数据分析的项目，了解到从R中调用Python的一个包，叫reticulate包，在R和Rmarkdown中都能使用，实现了R和Python对象之间的转换。想到我之前的工作，空间数据用python实现，其他数据分析则通过R代码实现，导致工作不连贯，两个程序来回换，代码的整理也比较乱。看到reticulate，瞬间有一种相见恨晚的感觉。

本文主要是参考sunshine_xxp的博客：https://blog.csdn.net/qq_31342997/article/details/89433255

为了便于自己之后的学习和review，我把一些内容整理到这里。

首先我现在用的Python是anaconda3环境下的Python。使用R调用python的时候，需要先再R中设定Python的运行环境。

# 在R中调用Python程序

```{r}
install.package("reticulate")
library(retuculate)
py_available() #检查系统是否安装过Python

##根据所安装的Python环境，选择使用use_condaenv or use_python

use_condaenv("D:/Program Files (X86)/Anaconda3")
use_python("D:/Program Files (X86)/Anaconda3/python.exe")
py_config() #查看python版本环境和anaconda以及numpy的信息
```

# 在R中导入python模块

在R下面可以通过import()导入Python模块，这个有区别于Python的import方式。同时访问具体模块下面的函数，需要用$符号，也是R下面的符号，这个和python也有区别。比如：

```{r}
import(numpy)
numpy$transpose(x)
```

# R与Python交互使用

使用repl_python()函数，就可以在R中进入Python的运行环境。使用exit退出python,回到R。其中在python环境下创建的对象，就存储到了py这个变量下面了。回到R环境后，通过查看和处理py，可以继续对数据进行分析。

同样，在python环境下也可以处理从R中获取的数据。比如说rdata数据集：

```{r}
repl_python()
import pandas as pd
pd.rdatta.describe()
pd.isnull(r.rdata.time)
exit
```

# 在R中载入python代码

如果你有一段写好的python代码，也可以直接通过R调用代码函数或者变量。

调用python函数.调用之后，可以直接在R环境下使用python代码里定义的函数，在R里完成计算。
```{r}
source_python()
```

直接获取python代码里的变量。
```{r}
py_run_file(”python代码路径“)
py_run_string()
```

# R与python的数据类型转换

Again，查看博客 https://blog.csdn.net/qq_31342997/article/details/89433255 里面有一些操作的例子，讲解很清晰。
![](/Fig/20200921.jpg)

# rmarkdown里调用python

从rmarkdown里调用python就方便很多了，可以通过我们前面的方法实现。比如：

```
```{r setup, include=FALSE}
library(reticulate)
use_python()
```

也可以直接在markdown里面嵌入python chunk，chunk里面的python code就按照python的语法来写。

```{python}
```[python]
import pandas
flight = pandas.read_csv()
print(flight)

import matplotlib.pyplot as plt
import numpy as np
```

# 从python中调用R

另外，我还看到可以从python中调用R，实现R的数据集、函数和包在python环境下运行。我平时主要用R，对python使用不多，只有分析空间数据或遥感数据的时候，会多用python，所以主要是从R中调用python的结果，这块内容可参考的相关介绍同样来自sunshine_xxp（非常感谢！）：https://blog.csdn.net/qq_31342997/article/details/89428158


最近还学到了很多内容：比如r和github联动，r或python与Google earth engine联动，与tensorflow等等，需要慢慢学习。


