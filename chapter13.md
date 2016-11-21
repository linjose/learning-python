# 13.粄醚夹非家舱畐

###13-1.絤策ㄏノ夹非家舱畐
  * 把σ﹛よ夹非家舱畐ゅン: https://docs.python.org/2/library/index.html
  * 絤策ㄏノ: `time``datetime`
    * time
```
>>> import time
>>> time.time()
```
    * datetime
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



###13-2.更家舱畐
  *  ubuntu い更 `psutil`ㄏノウ糶菏北╰参:
    * よ猭: `sudo apt-get install python-psutil`
    * よ猭: `sudo pip install psutil`
  * ㄏノ弧: https://pypi.python.org/pypi/psutil
  * 絛ㄒ祘Α:
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