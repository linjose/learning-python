# 12.�۩w�q�Ҳ�

###12-1.import �ۦ�}�o�禡
�N���q�{���x�s�� mygcd.py 
```
def gcd(x,y):
	g = y
	while x > 0:
		g = x
		x = y % x
		y = g
	return g
```
�èϥΤ�
```
import mygcd
...
```
