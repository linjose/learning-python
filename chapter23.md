# 23.Python製作爬蟲

###23-1.lxml 抓 Yahoo 新聞
  * 作法可參考：http://tech-marsw.logdown.com/blog/2016/01/10/crawler-index
  * 測試資料新聞來源: https://tw.news.yahoo.com/%E6%B0%B4%E9%87%8C%E9%83%B5%E5%B1%80%E6%96%B0%E5%B1%80%E5%B1%8B-%E6%8F%AD%E7%89%8C-160000988.html

```
# encoding: utf-8

import urllib2
from lxml import etree

from HTMLParser import HTMLParser
class MLStripper(HTMLParser):
    def __init__(self):
        self.reset()
        self.fed = []
    def handle_data(self, d):
        self.fed.append(d)
    def get_data(self):
        return ''.join(self.fed)

def strip_tags(html):
    try:
        s = MLStripper()
        s.feed(html)
        return s.get_data()
    except:
        return html

request = urllib2.Request("https://tw.news.yahoo.com/%E6%B0%B4%E9%87%8C%E9%83%B5%E5%B1%80%E6%96%B0%E5%B1%80%E5%B1%8B-%E6%8F%AD%E7%89%8C-160000988.html")
response = urllib2.urlopen(request)
html = response.read()

page = etree.HTML(html)

ret = []
for txt in page.xpath(u"//p/text()"):
     ret.append(txt)

print "title: ", page.xpath(u"//h1/text()")[0]
print "content: ", " ".join(ret)

```


###23-2.將爬文結果寫入DB
  - 將資料調整為以下格式，並塞入mLab中
  ```
  {"title":"水里郵局新局屋 揭牌", "content":"水里郵局新局屋...生活。"}
  ```
