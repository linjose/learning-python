# 4.��ƫ��A�P�ܼ�

###4-1.�򥻿�X
```
>>> name = "Henry"
>>> age = 24
# �i�H�� , ���j�h���ܼƤ@�_��X
>>> print "Hello,",name,"is",age,"years old."
# �]�i�H�� + ���n�`�N���A
>>> print "Hello, " + name + " is " + str(age) + " years old.��
```
###4-2.�򥻿�J
```
>>> s = input("Please enter a number: ")
Please enter a number: 123
>>> print "The number is ", s, s.__class__
The number is  123 <type 'int��>
```
###4-3.��ƫ��A-�ƭ�/�r��/���L
  * ���եH�Uint, long, float, complex�|�L�X����
```
>>> type(1)      # 1 �O���򫬺A�H
>>> type(1L)     # �[�W L �O�H
>>> type(2 ** 64 - 1) 
>>> type(2 ** 64 + 1) 
>>> type(3.14)   # �B�I�ƬO float ���A
>>> type(3 + 4j) # �䴩�Ƽƪ� complex ���A
>>> 2 ** 100     # 2 �� 100 ����
>>> type(True)   
>>> type('abc')
```
  * ���եH�Ustring�|�L�X����
```
print "Hello world!"        
print "Hello\tworld!"       
print "John's Treasure!"     
print 'Hello world!'       
print 'Hello\tworld!'      
print 'John\'s "Treasure"!' 
```
  * �m��:
```
>>> s = 'I have an apple, I have a pen.'
>>> print s[...] + s[...]
applepen
```


###4-4.��ƫ��A-�e��
  * list 
    1. �бN John ���� Mary
  ```
  mylist = ['My', 'name', 'is', 'John']
  ```
    2. �ϥ�`mylist.append('')`�b�y�l�����ݥ[�J�T�ĸ��A�A`print`�ݷ|�����򵲪G
    3. ��`" ".join(mylist)`�L�X�ܦ��y�l
  * tuple
    * �ոլݭק�ȷ|����
    ```
    t = (1, 2.0, "3", [4], (5))
    t[1] = 2
    ```
  * dict
    * ��dict�إߥH�U��ơG
      * 'name':'John'
      * 'age':18
      * 'phone':'0987-654-321'

