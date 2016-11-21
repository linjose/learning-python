# 13.�{�ѼзǼҲծw

###13-1.�m�ߨϥμзǼҲծw
  * �Ѧҩx��зǼҲծw���: https://docs.python.org/2/library/index.html
  * �m�ߨϥ�: `time`�B`datetime`
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



###13-2.�U���Ҳծw
  * �b ubuntu ���U�� `psutil`�A�ϥΥ��g�ʱ��t��:
    * ��k�@: `sudo apt-get install python-psutil`
    * ��k�G: `sudo pip install psutil`
  * �ϥλ���: https://pypi.python.org/pypi/psutil
  * �d�ҵ{��:
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