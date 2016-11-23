# 17.開發API

###17-1.使用 Flask
  - 在 linux 環境中安裝 Flask
```
pip install Flask
```
  - 建立一檔案 `vim hello_生日四碼.py` 輸入以下內容，並儲存

```
from flask import Flask
app = Flask(__name__)

@app.route("/")
def hello():
    return "Hello World!"

if __name__ == "__main__":
    app.run(host='0.0.0.0', port=生日+10000)
```

  - 啟動 Flask `python hello_生日四碼.py` 並用網頁開啟 `http://ip:port/` 即可看到您的 API
    - port 即為 `生日+10000`

###17-2.增加 Flask API 路徑
  - 增加一路徑`status`輸入以下內容，並儲存

```
@app.route("/status")
def status():
    return '{"status":1}'
```
  - 重新啟動flask，並開啟網頁`http://ip:port/status` 即可看見新增路徑的 api

###17-3.取得 Flask API 參數
  - 在 `import` 部分增加 `request` 模組

```
from flask import Flask, request
```

  - 增加兩路徑`api`與`api2`，輸入以下內容並儲存

```
@app.route('/api')
def api():
    return '{"param":'+str(request.args.get('abc'))+'}'

@app.route('/api2')
def api2():
    return request.args.items().__str__()
```
  - 重新啟動flask，並開啟網頁進行結果測試
    - API: `http://ip:port/api?abc="hello" `
    - API1: `http://ip:port/api2?abc="hello"&efg="world" `

###17-4. Flask API 連結外部資料源
  - 將 `14.實作體驗` 的 Open Data 拿來做資料源

```
import json
import urllib
```
```
url = "http://data.taipei/opendata/datalist/apiAccess?scope=resourceAquire&rid=201d8ae8-dffc-4d17-ae1f-e58d8a95b162"

response = urllib.urlopen(url)
data = json.loads(response.read())
print data
```
  - 改寫成 Flask 的 function
    - 要先增加 `import json, urllib`
    - 再增加以下內容

```
@app.route('/od')
def od():
    api_type = request.args.get('type')
    if api_type == 'show':
        ret = show()
    else:
        ret = test()
    return ret

def test():
    return '{"test":1}'

def show():
    url = "http://data.taipei/opendata/datalist/apiAccess?scope=resourceAquire&rid=201d8ae8-dffc-4d17-ae1f-e58d8a95b162"
    response = urllib.urlopen(url)
    data = json.loads(response.read())
    return str(data).replace('u\'','').decode('unicode_escape')
```
  - 重新啟動flask，並開啟網頁進行結果測試
    - `http://ip:port/od?type=test`
    - `http://ip:port/od?type=show`
