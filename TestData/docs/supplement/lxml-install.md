---
title: 08-lxml 的安装
date: 2022-12-20 21:13:14
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

lxml 是 Python 的一个解析库，支持 HTML 和 XML 的解析，支持 XPath 解析方式，而且解析效率非常高，本节我们了解下它的安装方式，分为 Windows、Linux、Mac 三大平台来介绍。

## 相关链接

- 官方网站：[http://lxml.de](http://lxml.de/)
- GitHub：[https://github.com/lxml/lxml](https://github.com/lxml/lxml)
- PyPi：[https://pypi.python.org/pypi/lxml](https://pypi.python.org/pypi/lxml)

## 安装方法

### Windows 下的安装

Windows 下可以先尝试利用 pip3 安装，直接执行如下命令即可：

```python
pip3 install lxml
```

如果没有任何报错则证明安装成功。

如果出现报错，比如提示缺少 libxml2 库等信息，可以采用 wheel 方式安装。

推荐直接到这里下载对应的 wheel 文件，链接为：[http://www.lfd.uci.edu/~gohlke/pythonlibs/#lxml](http://www.lfd.uci.edu/~gohlke/pythonlibs/#lxml)，找到本地安装 Python 版本和系统对应的 lxml 版本，例如 Windows 64 位 Python3.6 就选择 `lxml‑3.8.0‑cp36‑cp36m‑win_amd64.whl`，以此类推，将其下载到本地。

然后利用 pip3 安装即可，命令如下：

```python
pip3 install lxml‑3.8.0‑cp36‑cp36m‑win_amd64.whl
```

这样我们就可以成功安装好 lxml 了。

### Linux 下的安装

在 Linux 平台下安装问题不大，同样可以先尝试 pip3 安装，命令如下：

```python
pip3 install lxml
```

如果报错，可以尝试下方的解决方案。

#### CentOS、RedHat

对于此类系统，报错主要是因为缺少必要的库。

执行如下命令安装所需的库即可：

```shell
sudo yum groupinstall -y development tools
sudo yum install -y epel-release libxslt-devel libxml2-devel openssl-devel
```

主要是 libxslt-devel libxml2-devel 这两个库，lxml 依赖于它们。安装好了之后重新尝试 Pip 安装即可。

#### Ubuntu、Debian、Deepin

报错的原因同样可能是缺少了必要的类库，执行如下命令安装：

```shell
sudo apt-get install -y python3-dev build-essential libssl-dev libffi-dev libxml2 libxml2-dev libxslt1-dev zlib1g-dev
```

安装好了之后重新尝试 pip 安装即可。

### Mac 下的安装

在 Mac 平台下，仍然可以首先尝试 pip3 安装，命令如下：

```python
pip3 install lxml
```

如果产生错误，可以执行如下命令将必要的类库安装：

```shell
xcode-select --install
```

之后再重新运行 pip3 安装就没有问题了。

lxml 是一个非常重要的库，比如 BeautifulSoup、Scrapy 框架都需要用到此库，所以请一定安装成功。

## 验证安装

安装完成之后，可以在 Python 命令行下测试。

```shell
$ python3
>>> import lxml
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