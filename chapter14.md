# 14.實作體驗

###14-1.連接 Open Data
#### step 1. 選擇資料源
以「臺北市今日施工資訊」API存取為例，本例實作選擇json資料型態。
  - TPE OD: http://data.taipei/opendata/datalist/datasetMeta/outboundDesc?id=4d29818c-a3ee-425d-b88a-22ac0c24c712&rid=201d8ae8-dffc-4d17-ae1f-e58d8a95b162
  - JSON Pretty 工具: http://json.parser.online.fr/



#### step2.選擇輸出資料
1. 本題練習輸入建立一檔案 `workday.py`
2. 輸入指定日期，回傳該日期是否有施工結果
  - `python workday.py 1051119`
  - `python workday.py 1060413`
3. 設計輸出資訊包含:
  - 施工單位(APP_NAME): `str`
  - 行政區(C_NAME): `str`
  - 施工位置(ADDR): `str`
  - 工程內容(NPURP): `str`
  - 核准施工起日(CB_DA): `int`
  - 核准施工迄日(CE_DA): `int`

#### step3.使用以下程式碼接上API
使用urllib模組取得API回傳內容，再用json模組解析。
```
import json
import urllib

url = "http://data.taipei/opendata/datalist/apiAccess?scope=resourceAquire&rid=201d8ae8-dffc-4d17-ae1f-e58d8a95b162"

response = urllib.urlopen(url)
data = json.loads(response.read())
print data
```
#### step4.設計成自己的功能
如step2所敘述，解析`data`，做成可查詢某時段有哪些路段在施工。
```
#-*- coding: utf-8 -*-
import json
import urllib
import sys

# argv 取得查詢日期

url = "http://data.taipei/opendata/datalist/apiAccess?scope=resourceAquire&rid=201d8ae8-dffc-4d17-ae1f-e58d8a95b162"

response = urllib.urlopen(url)
data = json.loads(response.read())
print data

# 用 for 迴圈解析資料
# 以下兩項放在if條件式中，作為查詢條件項目:
# data['result']['results'][i]['CB_DA']
# data['result']['results'][i]['CE_DA']
# 若符合條件，則輸出施工單位、行政區、施工位置、工程內容、核准施工起日、核准施工迄日。
```

#### step5.可以包成json格式輸出
```
res = []
for ... :
    if ... :
        res.append({u'施工單位':raw[i]['APP_NAME'], u'施工位置':raw[i]['ADDR']}...)

print json.dumps(res).decode('unicode_escape')
```


###14-2.連接 Open Data CSV
  - 找一個 CSV 的 Open Data，並且用 `wget http://...../xxx.csv` 下載至VM中
  - 參考以下程式碼，實作讀寫Open Data CSV檔的程式(`delimiter`是分隔符號(欄與欄的分隔)，`quotechar`是把欄位內容包起來的符號): 
```
>>> import csv
>>> with open('eggs.csv', 'rb') as csvfile:
...     spamreader = csv.reader(csvfile, delimiter=',', quotechar='"')
...     for row in spamreader:
...         print ', '.join(row)
Spam, Spam, Spam, Spam, Spam, Baked Beans
Spam, Lovely Spam, Wonderful Spam
```
