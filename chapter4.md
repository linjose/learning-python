# 4.資料型態與變數

###4-1.基本輸出
```
>>> name = "Henry"
>>> age = 24
# 可以用 , 分隔多個變數一起輸出
>>> print "Hello,",name,"is",age,"years old."
# 也可以用 + 但要注意型態
>>> print "Hello, " + name + " is " + str(age) + " years old.”
```
###4-2.基本輸入
```
>>> s = input("Please enter a number: ")
Please enter a number: 123
>>> print "The number is ", s, s.__class__
The number is  123 <type 'int‘>
```
###4-3.資料型態-數值/字串/布林
  - 測試以下int, long, float, complex會印出什麼
```
>>> type(1)      # 1 是什麼型態？
>>> type(1L)     # 加上 L 呢？
>>> type(2 ** 64 - 1) 
>>> type(2 ** 64 + 1) 
>>> type(3.14)   # 浮點數是 float 型態
>>> type(3 + 4j) # 支援複數的 complex 型態
>>> 2 ** 100     # 2 的 100 次方
>>> type(True)   
>>> type('abc')
```
  - 測試以下string會印出什麼
```
print "Hello world!"        
print "Hello\tworld!"       
print "John's Treasure!"     
print 'Hello world!'       
print 'Hello\tworld!'      
print 'John\'s "Treasure"!' 
```
  - 練習:
```
>>> s = 'I have an apple, I have a pen.'
>>> print s[...] + s[...]
applepen
```


###4-4.資料型態-容器
  - list 
    1. 請將 John 換成 Mary
  ```
  mylist = ['My', 'name', 'is', 'John']
  ```
    2. 使用`mylist.append('')`在句子的末端加入禁嘆號，再`print`看會有什麼結果
    3. 用`" ".join(mylist)`印出變成句子
  - tuple
    * 試試看修改值會怎麼樣
    ```
    t = (1, 2.0, "3", [4], (5))
    t[1] = 2
    ```
  - dict
    * 用dict建立以下資料：
      * 'name':'John'
      * 'age':18
      * 'phone':'0987-654-321'

