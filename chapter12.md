# 12.自定義模組

###12-1.import 自行開發函式
將此段程式儲存為 mygcd.py 
```
def gcd(x,y):
	g = y
	while x > 0:
		g = x
		x = y % x
		y = g
	return g
```
並使用之
```
import mygcd
...
```
