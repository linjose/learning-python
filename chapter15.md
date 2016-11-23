# 15.Python PaaS平台

###15-1.註冊 PythonAnyWhere
  1. 進入 http://www.pythonanywhere.com 
  2. 點選右上角 `Log in`連結
  3. 進入Log in頁面後，再點選`Sign up here`連結
  4. 填入註冊資訊，打勾`I agree...`，並按下`Register`
  5. 完成註冊後，必須先進行 Email 認證，才能開始使用。

###15-2.操作 PythonAnyWhere
#### Practice#1. 操作 Consoles
  * 點選上方頁籤的 `Consoles`
##### Python 2.7 Console
  1. 在`Start a new console`點選`Python2.7`連結
  2. 進入 Python interpreter 後，試著使用該環境，例如輸入以下內容，以熟習環境：
```
# 列印測試
print "Hello PythonAnyWhere"
```
```
# 測試 import 時間
import time
time.time()
```
```
# 測試昨日的
import psutil
psutil.cpu_times()
# 輸出結果不會顯示真實狀況，因為是雲端環境
# scputimes(user=0.0, nice=0.0, system=0.0, idle=0.0, iowait=0.0, irq=0.0, softirq
=0.0, steal=0.0, guest=0.0)
```
```
# 離開
exit()
```

##### Linux Console
  1. 在`Start a new console`點選`Bash`連結
  2. 進入 Linux Console 後，輸入以下指令：
```
# 查看現有檔案列表
ls
```
```
# 查看現有檔案詳細資訊
ls -l
```
```
# 寫入檔案
echo "Hello PythonAnyWhere" > hello.txt
# 查詢是否有建立檔案成功
ls
cat hello.txt
```
```
# 啟動vim編輯器(跳出: ESC->:q)
vim hello.txt
```
```
# 離開
exit
```

#### Practice#2. 操作 Files
  1. 在`Directories`底下建立一個資料夾叫做`mydir`
  2. 在`Files`建立一個檔案，叫做`hello.py`，內容為
```
print "hello file testing..."
```
  3. 直接按右上角`Save`，再回到`Console`開啟 `bash`，進到`mydir`測試執行`hello.py`
```
cd mydir/
python hello.py
```

#### Practice#3. 操作 Web
  * 此部分會在 `17.開發API` 進行
