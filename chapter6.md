# 6.�B�⦡�P���z

### 6-1.�ʤ�ާ@

1. ���@��²���p���
2. �إߤ@�ɮסA�W�� `mycal.py`
3. �ϥ� `sys.argv[]` ���o `mycal.py` ���Ѽ�
4. �Ѽƪ���J�覡�� `python mycal.py 1 + 1`

```
import sys

operand1 = sys.argv[1] # �ק�type
operator = sys.argv[2] 
operand2 = sys.argv[3] # �ק�type

print sys.argv[0] #�ݬݵ��G�O����

if operator is '+':
    # �Цb���C�L���G
elif operator is '-':
    # �Цb���C�L���G
elif operator is '*':
    # �Цb���C�L���G
elif operator is '/':
    # �Цb���C�L���G
else:
    print "ERROR"
```