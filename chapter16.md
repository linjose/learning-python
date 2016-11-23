# 16.DBaaS 平台

###16-1.mLab
  - 登入: http://mlab.com/
  - 申請 mlab 帳號
  - 建立 db: mydb
  - 建立 collection: mycoll
  - 插入以下資料:
  ```
  {"name": "John", "age": 20, "loc":"Taipei"}
  {"name": "Tom", "age": 22, "loc":"Taichung"}
  {"name": "Max", "age": 23, "loc":"Tainan"}
  {"name": "Ken", "age": 19, "loc":"Taipei"}
  {"name": "Rex", "age": 20, "loc":"Tainan"}
  ```
  - 建立登入帳號用的使用者: demo/demo

###16-2.ElephantSQL
- 登入: https://www.elephantsql.com/
- 申請 ElephantSQL 帳號
- 申請 DB Instances
- 操作以下指令
  - CREATE 
    ```
    CREATE TABLE user (id TEXT PRIMARY KEY, key TEXT);
    ```
  - INSERT
    ```
    INSERT INTO user VALUES ('John', 'John123!');
    INSERT INTO user VALUES ('Tom', 'Tom123!');
    INSERT INTO user VALUES ('Max', 'Max123!');
    ```
  - SELECT
    ```
    SELECT * FROM user;
    ```
  - UPDATE
    ```
    UPDATE user SET key = 'Max456!' WHERE id = 'Max'; 
    ```
  - DELETE
    ```
    DELETE FROM user WHERE id = 'Tom';
    ```
