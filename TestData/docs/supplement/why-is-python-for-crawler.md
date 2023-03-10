---
title: 03-为什么写网络爬虫天然就是择Python而用
date: 2022-11-21 16:06:16
author: 王平
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

关于这个问题，老猿就先从自己的经历讲起吧。很多年前，大约11年前，老猿我接手了一个搜索引擎的网络爬虫，那是一个用 C++ 写的通用搜索引擎的爬虫。C++ 的语言，多线程的实现，爬虫的运行效率非常高。但是，找bug很困难，实现新的功能很繁琐。

记得有次发现有些网页抓不下来，开始好久都找不着头脑，废了九牛二虎之力，终于发现是 http 请求处理的问题。深入代码才看到， http 协议的这部分代码都是写这个人自己实现的，只是实现了最基本的协议，也就是，建立 socket 连接，发送请求，然后通过 socket 接收数据，解析响应头（response headers）。然而这个响应头连 http 重定向都没有处理，凡是重定向的响应就都失败了，自然那些网页就抓不下来了。

为了抓到那些响应，我们就不得不继续完善 http 协议的解析功能，贡献了很多代码～～

为什么要自己实现基本的 http 协议呢？难道就没有好的第三方库可以用吗？现在想来，那个爬虫也就是看上去能用，听上去高大上，实际上问题很多。

那个网络爬虫程序维护了一两年最终放弃了，后来的爬虫技术都开始用 Python 来实现了。

现在如果让我实现一个网络爬虫，二话不说，肯定是要用 Python。究其原因，可能有已经几点经验和教训跟小猿们分享一下。

## 1. 变幻莫测的网络爬虫

写过爬虫的猿猿们可能都有这么一个感觉，就是昨天跑的好好的爬虫，今天可能就出问题，不 work 了。这里面的原因可能就是，网页的改版，网站的封锁等等。遇到这种情况，我们就必须在最快的时间内调试找出问题所在，并以最快的速度修复，使其尽快上线跑起来。

## 2. 随机应变的 Python 

鉴于上述爬虫复杂的变化，写网络爬虫就必须依赖一个快速开发、灵活的语言，同时又有完整丰富的库支撑。而同时具备这些优点的语言，无疑就是 Python 了。所以，**Python 天然就是为爬虫而生，爬虫天然就是择 Python 而用。**

## 3. 简洁丰富的 Python

看到 Python 和网络爬虫这种天然相连的关系，小猿们不禁要问，Python 适合网络爬虫的天然属性都是哪些呢？不急，听老夫慢慢道来。

### 3.1 简洁的语法

Python 的语法非常简单，提倡简洁而不简单，Python 开发者的哲学就是“用一种方法，最好是只有一种方法来做一件事”，这种哲学让你写的代码没有太多个人风格，易于让他人看懂你的代码，也让你轻易看懂别人的代码。Python 的简洁，也让开发者可以仅用几行代码就实现一个功能，而同样的功能用Java可能要几十行上百行，要用 C++ 可能是几百行。

小猿们可以试试在 Python 解释器里面运行 `import this`，来品味一下 Python 的哲学：

```python
>>> import this
> The Zen of Python
> by Tim Peters

> Beautiful is better than ugly.
> Explicit is better than implicit.
> Simple is better than complex.
> Complex is better than complicated.
> Flat is better than nested.
> Sparse is better than dense.
> Readability counts.
> Special cases aren't special enough to break the rules.
> Although practicality beats purity.
> Errors should never pass silently.
> Unless explicitly silenced.
> In the face of ambiguity, refuse the temptation to guess.
> There should be one-- and preferably only one --obvious way to do it.
> Although that way may not be obvious at first unless you're Dutch.
> Now is better than never.
> Although never is often better than *right* now.
> If the implementation is hard to explain, it's a bad idea.
> If the implementation is easy to explain, it may be a good idea.
> Namespaces are one honking great idea -- let's do more of those!
```

Python简洁的语法，让你实现、修改爬虫都变得轻松起来。也就是说，写起来贼快！人生苦短，何不Python 🙂

### 3.2 丰富的 Python 模块

小猿们应该已经听说过 Python 模块（库）的丰富性，或许只是还没有时间和机会接触过那么多而已。这里，身经百战、见多识广的老猿给你撂下一句话：“几乎所有你想要的功能 Python 都有库实现了”。这句话，似乎很狂妄，但满足你 90% 的需求没问题。所以，小猿们要记住这句话，在以后的开发过程中，需要什么基本功能了，就不妨先去搜搜、问问，看看是不是已经有人实现了这个功能，并且上传到pypi上了，而你要做到可能仅仅是 `pip install`。同时，也验证一下这句话是不是那么回事儿。

比方说，

我要下载网页就用，

Python 标准模块 `urllib.request`，还有好的没话说的第三方开源模块 `requests`

异步 http 请求的有 aiohttp

我要处理网址 url 就用：

Python自带的模块 `urllib.parse`

我要解析 html 就用：

基于 C 语言库的高效率模块 `lxml`, 好用的 `beautifulsoap`。

我要管理网址，记录下载成功的、失败的、未下载的各种 url 的状态，就用：Python 封装的 key-value 数据库 leveldb 

我要用成熟的爬虫框架，就用：

历史悠久的 `scrapy`，后起之秀 `pyspider`。

我要支持 javascript 和 ajax，就用：

浏览器模拟框架 Selenium，加上不需要桌面环境跑着 Linux 服务器上的大名鼎鼎的 Google Headless Chrome。

还有个 Phantomjs，可惜已经停止开发了。

以上，只是老猿用过的写网络爬虫需要的一些基本模块，具体实践中需要的基本功能都可以先搜搜看，没准儿就已经有模块支持想要的功能了。还是那句话，“几乎所有你想要的功能 Python 都有库实现了”。你的工作，就是像搭积木一样，把他们有机结合在一起实现你的业务逻辑。

对的，像搭积木一样实现你的网络爬虫，为什么不选择 Python 呢？

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