---
title: 07-pyquery 的安装
date: 2022-12-20 16:57:23
author: AI悦创
isOriginal: true
category: Python 网络爬虫专栏
tag:
    - Crawler
icon: debug
sticky: false
star: false
article: true
timeline: true
image: false
navbar: true
sidebarIcon: true
headerDepth: 5
comment: true
lastUpdated: true
editLink: false
backToTop: true
toc: true
---

你好，我是悦创。

pyquery 同样是一个强大的网页解析工具，它提供了和 jQuery 类似的语法来解析 HTML 文档，支持 CSS 选择器，使用非常方便。本节中，我们就来了解一下它的安装方式。

## 1. 相关链接

- GitHub：[https://github.com/gawel/pyquery](https://github.com/gawel/pyquery)
- PyPI：[https://pypi.python.org/pypi/pyquery](https://pypi.python.org/pypi/pyquery)
- 官方文档：[http://pyquery.readthedocs.io](http://pyquery.readthedocs.io/)

## 2. pip 安装

这里推荐使用 pip 安装，命令如下：

```
pip3 install pyquery
```

命令执行完毕之后即可完成安装。

## 3. wheel 安装

当然，我们也可以到 PyPI（[https://pypi.python.org/pypi/pyquery/#downloads](https://pypi.python.org/pypi/pyquery/#downloads)）下载对应的 wheel 文件安装。比如如果当前版本为 1.2.17，则下载的文件名称为 `pyquery-1.2.17-py2.py3-none-any.whl`，此时下载到本地再进行 pip 安装即可，命令如下：

```python
pip3 install pyquery-1.2.17-py2.py3-none-any.whl
```

## 4. 验证安装

安装完成之后，可以在 Python 命令行下测试：

```python
$ python3
>>> import pyquery
```

如果没有错误报出，则证明库已经安装好了。

欢迎关注我公众号：AI悦创，有更多更好玩的等你发现！

::: details 公众号：AI悦创【二维码】

![](/gzh.jpg)

:::

::: info AI悦创·编程一对一

AI悦创·推出辅导班啦，包括「Python 语言辅导班、C++ 辅导班、java 辅导班、算法/数据结构辅导班、少儿编程、pygame 游戏开发、Web全栈、Linux」，全部都是一对一教学：一对一辅导 + 一对一答疑 + 布置作业 + 项目实践等。当然，还有线下线上摄影课程、Photoshop、Premiere 一对一教学、QQ、微信在线，随时响应！微信：Jiabcdefh

C++ 信息奥赛题解，长期更新！长期招收一对一中小学信息奥赛集训，莆田、厦门地区有机会线下上门，其他地区线上。微信：Jiabcdefh

方法一：[QQ](http://wpa.qq.com/msgrd?v=3&uin=1432803776&site=qq&menu=yes)

方法二：微信：Jiabcdefh

:::

![](/zsxq.jpg)