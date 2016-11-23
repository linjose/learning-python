# 6.運算式與陳述

### 6-1.動手操作
1. 做一個簡易計算機
2. 建立一檔案，名為 `mycal.py`
3. 使用 `sys.argv[]` 取得 `mycal.py` 的參數
4. 參數的輸入方式為 `python mycal.py 1 + 1`

```
import sys

operand1 = sys.argv[1] # 修改type
operator = sys.argv[2] 
operand2 = sys.argv[3] # 修改type

print sys.argv[0] #看看結果是什麼

if operator is '+':
    # 請在此列印結果
elif operator is '-':
    # 請在此列印結果
elif operator is '*':
    # 請在此列印結果
elif operator is '/':
    # 請在此列印結果
else:
    print "ERROR"
```
