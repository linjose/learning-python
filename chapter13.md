# 13.認識標準模組庫

###13-1.練習使用標準模組庫
  - 參考官方標準模組庫文件: https://docs.python.org/2/library/index.html
  - 練習使用: `time`、`datetime`
    - time
```
>>> import time
>>> time.time()
```
    - datetime
```
>>> import datetime
>>> now = datetime.datetime.now()
>>> print now
>>> print now.year
>>> print now.month
>>> datetime.datetime.now().date()
>>> datetime.datetime.now().strftime("%Y-%m-%d %H:%M:%S")
>>> datetime.date.today() + datetime.timedelta(days=1)
>>> datetime.datetime.now() - datetime.timedelta(days=3)
>>> datetime.datetime.strptime("2016-12-31 18:20:10", "%Y-%m-%d %H:%M:%S")
```



###13-2.下載模組庫
  - 在 ubuntu 中下載 `psutil`，使用它寫監控系統:
    - 方法一: `sudo apt-get install python-psutil`
    - 方法二: `sudo pip install psutil`
  - 使用說明: https://pypi.python.org/pypi/psutil
  - 範例程式:
```
>>> import psutil
>>> psutil.cpu_times()
scputimes(user=3961.46, nice=169.729, system=2150.659, idle=16900.540, iowait=629.59, irq=0.0, softirq=19.42, steal=0.0, guest=0, nice=0.0)
>>>
>>> for x in range(3):
...     psutil.cpu_percent(interval=1)
...
4.0
5.9
3.8
```
