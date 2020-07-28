# DEBUG: Forbidden by robots.txt

有些网站跟目录中有`robots.txt`，用于申明不让爬虫爬取。所以Scrapy默认就是遵守协议，不爬取这些网站。

为了能继续爬取，则需要去设置：

```
ROBOTSTXT_OBEY = False
```

即可。
