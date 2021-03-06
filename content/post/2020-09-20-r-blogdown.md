---
title: 关于r-blogdown
author: 笙箫Sophie
date: '2020-09-20'
slug: r-blogdown
categories:
  - R
tags:
  - R
---
这是本博客的第一篇文章。

这个博客通过R下的blogdown包创建，也算是我在Rmarkdown应用下的一个探索和练习。所以第一篇文章也顺便把这两天的发现总结一下。

首先要说明的是，R markdown下面有很多有用的包，可以实现写作、编程、发表一体化。开发者是大神谢益辉，愿景就是使写作者集中在文字创作上，画图和排版等重复的工作可以通过代码助力完成。我这两天大概试了试，发现确实很好用。

这些包运行的平台是在rmarkdown下，所以需要基本的rmarkdown，knitr和tinytex.

在这里总结的包是以下三个：

1. rticles

这个包里含有很多学术期刊的模板，可以直接加载模板在markdown里写文章。我最近正在用这个包，这样可以将自己的R代码插进文章里，这样修改代码生成新的图片后，就不需要输出再替换word里的图片，减少了很多繁琐的格式整理的工作。

相关的一些书籍和有用的网站：

__github:__ https://github.com/rstudio/rticles\
__R Markdown Cook:__ https://bookdown.org/yihui/rmarkdown-cookbook/\
__rmarkdown:__ https://bookdown.org/yihui/rmarkdown/\
https://vickysteeves.gitlab.io/repro-papers/r-markdown-in-reproducible-research.html

2. Bookdown

我也加载了bookdown，也就是说可以在R上整理书了。除了写作技术类书籍之外，我还看到了一些比较好的利用bookdown做技术类学习笔记的案例。所以自己之后的实践就是将数据类或者新技术类学习的内容，利用bookdown整理出来。


下面是一些有用的链接：

__bookdown制作发布的案例：__ https://bookdown.org/\
__bookdown使用指南：__ https://bookdown.org/yihui/bookdown/\
__RPubs:__ https://rpubs.com/ (rmarkdown发布的一些文档)\
https://blog.datascienceheroes.com/how-to-self-publish-a-book/\
__RStudio的Youtube Channel:__ https://www.youtube.com/channel/UC3xfbCMLCw1Hh4dWop3XtHg (这里有很多新的包的training和介绍，值得长期关注动态)

3. Blogdown

这个博客我就是用blogdown完成的。熟悉markdown的人用blogdown也会简单很多。操作和bookdown很类似，也是加载这个library后，建立一个新project,选择website Blog,就等于启动了blogdown.

以下也是相关的一些内容。

https://www.youtube.com/watch?v=CjTLN-FXiFA （这个视频有助于入门）\
https://www.youtube.com/watch?v=-9uuyJzWzCI （了解如何通过Netlify发布blog网站）\
https://bookdown.org/yihui/blogdown/ （关于blogdown的book）

现在我的了解就是掌握了这三个包，基本上可以在rmarkdown上面实现写文章、写书和写博客了。当然我还了解到也可以在R里面实现记者写报道的功能（尤其是涉及到数据的一些报道），我现在还没有探索这方面。

总之，Rmarkdown功能非常的强大，感觉有助于实现很好的知识管理和写作产出。

有一些可以参考的博客：

https://pzhao.org/zh/                                              

https://yufree.cn/                                                            

https://yihui.org/







