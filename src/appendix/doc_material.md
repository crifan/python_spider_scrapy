# 文档和资料

## Scrapy官网教程

* 英文
  * Scrapy 1.5 documentation — Scrapy 1.5.0 documentation
    * https://doc.scrapy.org/en/latest/index.html
* 中文
  * 新
    * Scrapy 1.0 文档(未完成,只更新了intro部分,请谨慎参考) — Scrapy 1.0.5 文档
      * http://scrapy-chs.readthedocs.io/zh_CN/1.0/
  * 旧
    * Scrapy 0.25 文档 — Scrapy 0.24.1 文档
        * https://scrapy-chs.readthedocs.io/zh_CN/latest/index.html
    * Scrapy入门教程 — Scrapy 0.24.6 文档
        * http://scrapy-chs.readthedocs.io/zh_CN/0.24/intro/tutorial.html

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

