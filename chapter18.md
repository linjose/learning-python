# 18.連接資料庫



###18-1.MongoDB
  - 安裝 MongoDB
```
sudo apt-get install mongodb-org
```
  - 安裝 pymongo 
```
sudo pip install pymongo
```
  - 使用python測試連接MongoDB

```
from pymongo import MongoClient 

# 建立連線
client = MongoClient()   #connect to default port on localhost 
# 選擇 DB
db = client['test']      #connect to the 'test' db
# 選擇 collection (Table)
collect = db['demo']

# 輸出一筆資料
print str(collect.find_one()).decode('unicode_escape')

# 輸出多筆資料
for ret in collect.find():
    print str(ret).decode('unicode_escape')

```
  - PyMongo範例: http://api.mongodb.com/python/current/api/pymongo/collection.html

###18-2.PostgreSQL
  - 安裝 PostgreSQL
```
sudo apt-get install postgresql-9.3 postgresql-server-dev-9.3
```
  - 安裝 psycopg2 
```
sudo pip install psycopg2
```
  - 使用 python 測試連接 PostgreSQL

```
import psycopg2
 
try:
    conn_str = "dbname='demo' user='demo' host='localhost' password='demo'"
    # 建立連線
    conn = psycopg2.connect(conn_str)
 
    # 建立一個psycopg2 cursor，來執行SQL
    cursor = conn.cursor()
 
    # 建立表
    cursor.execute("""CREATE TABLE usertable (name char(40));""")
 
     # 插入四筆資料
    cursor.execute("""INSERT INTO usertable VALUES('John'),('Josh'),('Joe'),('Joyce');""")
    
    # 查詢
    cursor.execute("""SELECT * from usertable""")
    rows = cursor.fetchall()
 
    print(rows)
except Exception as e:
    print("查無用戶，無法建立連線")
    print(e)
```
