# 14.��@����

###14-1.�s�� Open Data
#### step 1. ��ܸ�Ʒ�
�H�u�O�_������I�u��T�vAPI�s�����ҡA���ҹ�@���json��ƫ��A�C
  * TPE OD: http://data.taipei/opendata/datalist/datasetMeta/outboundDesc?id=4d29818c-a3ee-425d-b88a-22ac0c24c712&rid=201d8ae8-dffc-4d17-ae1f-e58d8a95b162
  * JSON Pretty �u��: http://json.parser.online.fr/



#### step2.��ܿ�X���
1. ���D�m�߿�J�إߤ@�ɮ� `workday.py`
2. ��J���w����A�^�ǸӤ���O�_���I�u���G
  * `python workday.py 1051119`
  * `python workday.py 1060413`
3. �]�p��X��T�]�t:
  * �I�u���(APP_NAME): `str`
  * ��F��(C_NAME): `str`
  * �I�u��m(ADDR): `str`
  * �u�{���e(NPURP): `str`
  * �֭�I�u�_��(CB_DA): `int`
  * �֭�I�u����(CE_DA): `int`

#### step3.�ϥΥH�U�{���X���WAPI
�ϥ�urllib�Ҳը��oAPI�^�Ǥ��e�A�A��json�ҲոѪR�C
```
import json
import urllib

url = "http://data.taipei/opendata/datalist/apiAccess?scope=resourceAquire&rid=201d8ae8-dffc-4d17-ae1f-e58d8a95b162"

response = urllib.urlopen(url)
data = json.loads(response.read())
print data
```
#### step4.�]�p���ۤv���\��
�pstep2�ұԭz�A�ѪR`data`�A�����i�d�߬Y�ɬq�����Ǹ��q�b�I�u�C
```
#-*- coding: utf-8 -*-
import json
import urllib
import sys

# argv ���o�d�ߤ��

url = "http://data.taipei/opendata/datalist/apiAccess?scope=resourceAquire&rid=201d8ae8-dffc-4d17-ae1f-e58d8a95b162"

response = urllib.urlopen(url)
data = json.loads(response.read())
print data

# �� for �j��ѪR���
# �H�U�ⶵ��bif���󦡤��A�@���d�߱��󶵥�:
# data['result']['results'][i]['CB_DA']
# data['result']['results'][i]['CE_DA']
# �Y�ŦX����A�h��X�I�u���B��F�ϡB�I�u��m�B�u�{���e�B�֭�I�u�_��B�֭�I�u����C
```

#### step5.�i�H�]��json�榡��X
```
res = []
for ... :
    if ... :
        res.append({u'�I�u���':raw[i]['APP_NAME'], u'�I�u��m':raw[i]['ADDR']}...)

print json.dumps(res).decode('unicode_escape')
```


###14-2.�s�� Open Data CSV
  * ��@�� CSV �� Open Data�A�åB�� `wget http://...../xxx.csv` �U����VM��
  * �ѦҥH�U�{���X�A��@Ū�gOpen Data CSV�ɪ��{��(`delimiter`�O���j�Ÿ�(��P�檺���j)�A`quotechar`�O����줺�e�]�_�Ӫ��Ÿ�): 
```
>>> import csv
>>> with open('eggs.csv', 'rb') as csvfile:
...     spamreader = csv.reader(csvfile, delimiter=',', quotechar='"')
...     for row in spamreader:
...         print ', '.join(row)
Spam, Spam, Spam, Spam, Spam, Baked Beans
Spam, Lovely Spam, Wonderful Spam
```