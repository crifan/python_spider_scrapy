# 简介

`Scrapy`是目前Python的最流行的爬虫框架。

TODO:

* [【整理】pyspider vs scrapy](http://www.crifan.com/python_spider_framework_pyspider_vs_scrapy)

## 基本原理

引用[别人](https://crazymouse.gitbooks.io/scrapy-with-python3/content/scrapy-spider-%E5%8E%9F%E7%90%86.html)总结的：

* 入口为`start_requests`方法或者`start_urls`数组
* `parse`方法一般用`yield`来生成一个`迭代器`，返回一个或多个`Request`/`Item`，或者二者都有
* 每个`Request`都会默认使用上次请求的`Cookies`信息
* 对于需登陆的数据，可以在`start_requests`中进行登陆
* 页面内常用`xpath`或者`css selecter`进行解析，也可以使用`BeautifulSoup`等其它工具
* `Spider`的数据请求部分叫`Downloader`，`Scrapy`是基于事件的，因此从宏观上讲，数据请求和响应是线程分离的
* `Spider`的结果用`pipeline`来进行处理，可以自定义各种`pipeline`，`pipeline`中可以对抓取到的`item`进行去重、数据存储等操作
* `Spider`与`Downloader`中间有一种叫做`middleware`的东西，进行管道式数据加工，有点类似于过滤器、代理之类的
* 随机`User_agent`就是通过`downloader middleware`来实现的


## 教程和资料

* 官网
  * [Scrapy | A Fast and Powerful Scraping and Web Crawling Framework](https://scrapy.org)
* Github
  * [scrapy/scrapy: Scrapy, a fast high-level web crawling & scraping framework for Python.](https://github.com/scrapy/scrapy)
* 教程
    * 中文
      * [crapy入门教程 — Scrapy 0.24.6 文档](https://scrapy-chs.readthedocs.io/zh_CN/0.24/intro/tutorial.html)
    * 英文
      * [Scrapy Tutorial — Scrapy 2.2.1 documentation](https://doc.scrapy.org/en/latest/intro/tutorial.html)
