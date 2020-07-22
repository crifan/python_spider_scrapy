# 简介

`Scrapy`是目前Python的最流行的爬虫框架。

TODO:

* [【已解决】Mac中PyCharm中找不到已安装的Scrapy库: No module named scrapy](http://www.crifan.com/mac_pycharm_cannot_found_installed_scrapy_lib_no_module_named_scrapy)
* [【记录】用Python的Scrapy去爬取Youtube中Humf的字幕](http://www.crifan.com/python_scrapy_crawl_youtube_humf_subtitle)
* [【记录】尝试Scrapy shell去提取cbeebies.com页面中的子url](http://www.crifan.com/scrapy_shell_try_extract_cbeebies_com_page_sub_url)
* [【已解决】scrapy中警告：DEBUG: Forbidden by robots.txt](http://www.crifan.com/scrapy_warning_debug_forbidden_by_robots_txt)
* [【已解决】Scrapy中丢失部分url链接没有抓取](http://www.crifan.com/scrapy_lost_some_url_link_not_crawl)
* [【已解决】Scrapy如何向后续Request的callback中传递参数](http://www.crifan.com/scrapy_pass_following_request_callback_parameter)
* [【已解决】Scrapy如何加载全部网页内容](http://www.crifan.com/scrapy_how_to_load_all_page_content)
* [【已解决】如何从Scrapy的Selector中获取html元素a的href属性的值](http://www.crifan.com/scrapy_selector_extract_html_element_a_href_value)
* [【已解决】Scrapy如何添加本地socks代理以便能打开Youtube网页](http://www.crifan.com/scrapy_how_add_local_socks_proxy_to_open_youtube_website)
* [【已解决】Scrapy的Python中如何解析部分的html字符串并格式化为html网页源码](http://www.crifan.com/scrapy_python_how_parse_partial_html_content_format_html_sourcecode)
* [【已解决】Mac中PyCharm中去加断点实时调试scrapy的项目](http://www.crifan.com/mac_pycharm_add_breakpoint_to_realtime_debug_scrapy_project)
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
