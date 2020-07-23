# Scrapy shell

Scrapy提供了一个命令行`shell`，用于无需新建爬虫项目，即可直接调试爬取页面。

下面举例介绍简单的用法。

爬取一个url=页面：

```bash
scrapy shell “http://global.cbeebies.com/shows/“
```

查看返回页面的body：

```python
response.body
```

查看头信息：

```python
response.headers
```

用[xpath](http://book.crifan.com/books/xpath_summary/website/)查找所需元素：

```python
response.xpath("//title")

response.xpath("//title").text()

response.xpath("//title").extract()

response.xpath("//title/text()").extract()
```


