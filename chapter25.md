# 25.Python RESTful API 在雲端

###25-1.實作 Open Data RESTful API
  - 將 flask 寫完的成果，放在 PythonAnyWhere 上
  - 並承23-2.連接 mLab，可直接在雲端上讀取 mLab 資料

###25-2.RESTful API製作概念
  - login: 使用RDB做帳密驗證，登入用
  - token: 放在Memory/In-Memory DB中，隨時取用，逾期則須重新登入
  - 其他即為查詢用API，視需求設計。
