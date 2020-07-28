# 基本用法

下面介绍Scrapy的基本用法。

## 官网快速教程

安装：

```bash
pip install scrapy
```

新建爬虫文件和写基本的代码：

```bash
cat > myspider.py <<EOF
import scrapy

class BlogSpider(scrapy.Spider):
    name = 'blogspider'
    start_urls = ['https://blog.scrapinghub.com']

    def parse(self, response):
        for title in response.css('.post-header>h2'):
            yield {'title': title.css('a ::text').get()}

        for next_page in response.css('a.next-posts-link'):
            yield response.follow(next_page, self.parse)
EOF
```

运行爬虫：

```bash
scrapy runspider myspider.py
```

更多细节可参考官网教程：

[Scrapy入门教程 — Scrapy 0.24.6 文档](https://scrapy-chs.readthedocs.io/zh_CN/0.24/intro/tutorial.html)
