# 丢失部分链接

[之前](https://www.crifan.com/scrapy_lost_some_url_link_not_crawl/)遇到过：本来有18个url，但是最终只抓取到8个，缺了10个。

原因：可能是被filter过滤掉了，也可能是爬取频率太快导致的

解决办法：

`youtubeSubtitle/settings.py`

中配置为：

```bash
# Configure a delay for requests for the same website (default: 0)
# See http://scrapy.readthedocs.org/en/latest/topics/settings.html#download-delay
# See also autothrottle settings and docs
# DOWNLOAD_DELAY = 3
DOWNLOAD_DELAY = 0.5
# The download delay setting will honor only one of:
CONCURRENT_REQUESTS_PER_DOMAIN = 16
CONCURRENT_REQUESTS_PER_IP = 16

# Configure item pipelines

# See http://scrapy.readthedocs.org/en/latest/topics/item-pipeline.html
ITEM_PIPELINES = {
   'youtubeSubtitle.pipelines.YoutubesubtitlePipeline': 300,
}
```

以及每个Request都加上`dont_filter=True`：

```python
yield scrapy.Request(url=groupUrl,
                     callback=self.parseEachYoutubeUrl,
                     dont_filter=True)


yield scrapy.Request(url=loadVideoUrl,
                     callback=self.parseLoadVideoResp,
                     method="POST",
                     dont_filter=True,
                     meta={"humfGroupTitle" : humfGroupTitle})

yield scrapy.Request(url=downloadUrl,
                     callback=self.parseDownloadSubtitlesResp,
                     meta=response.meta,
                     dont_filter=True)
```

即可解决问题，速度慢一点爬取，最终爬取到了所有的url。
