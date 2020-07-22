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

## 举例：新建cbeebies爬虫

```bash
scrapy startproject cbeebies

cd cbeebies

scrapy crawl Cbeebies
```

即可生成对应的html文件。

## help=帮助信息=语法

```bash
 ~  scrapy --help
Scrapy 2.2.1 - no active project

Usage:
  scrapy <command> [options] [args]

Available commands:
  bench         Run quick benchmark test
  commands
  fetch         Fetch a URL using the Scrapy downloader
  genspider     Generate new spider using pre-defined templates
  runspider     Run a self-contained spider (without creating a project)
  settings      Get settings values
  shell         Interactive scraping console
  startproject  Create new project
  version       Print Scrapy version
  view          Open URL in browser, as seen by Scrapy

  [ more ]      More commands available when run from project directory

Use "scrapy <command> -h" to see more info about a command
```

### startproject创建项目的help

```bash
~  scrapy startproject -h
Usage
=====
  scrapy startproject <project_name> [project_dir]

Create new project

Options
=======
--help, -h              show this help message and exit

Global Options
--------------
--logfile=FILE          log file. if omitted stderr will be used
--loglevel=LEVEL, -L LEVEL
                        log level (default: DEBUG)
--nolog                 disable logging completely
--profile=FILE          write python cProfile stats to FILE
--pidfile=FILE          write process ID to FILE
--set=NAME=VALUE, -s NAME=VALUE
                        set/override setting (may be repeated)
--pdb                   enable pdb on failure
```

