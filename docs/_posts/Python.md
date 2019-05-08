
# Python Overview

More details in Python for Everybody
https://www.py4e.com/

## 1. Variables
### 1) Don't need to pre-define variables


```python
x = 10
y = 10
res = x+y

print(x,y,res)
```

    10 10 20


## 2. Data structures

Data structures are classes which have many functions (methods)

### 1) String



```python
lab = 'MISL'
univ = 'SKKU'
print(lab + ' in ' + univ)
```

    MISL in SKKU



```python
print(lab.lower())
```

    misl



```python
# To see all the method you can use dir() function
print(dir(lab))
```

    ['__add__', '__class__', '__contains__', '__delattr__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__getnewargs__', '__gt__', '__hash__', '__init__', '__iter__', '__le__', '__len__', '__lt__', '__mod__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__rmod__', '__rmul__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', 'capitalize', 'casefold', 'center', 'count', 'encode', 'endswith', 'expandtabs', 'find', 'format', 'format_map', 'index', 'isalnum', 'isalpha', 'isdecimal', 'isdigit', 'isidentifier', 'islower', 'isnumeric', 'isprintable', 'isspace', 'istitle', 'isupper', 'join', 'ljust', 'lower', 'lstrip', 'maketrans', 'partition', 'replace', 'rfind', 'rindex', 'rjust', 'rpartition', 'rsplit', 'rstrip', 'split', 'splitlines', 'startswith', 'strip', 'swapcase', 'title', 'translate', 'upper', 'zfill']


### 2) List
List is similar with linked list. (eg. vector in c++)


```python
a = [4, 3, 5, 2, 1]
print(a)
print(len(a))
```

    [4, 3, 5, 2, 1]
    5


You can index and slice list


```python
print(a[0])
print(a[:3]) #from 0 to 3, but not including 3
```

    4
    [4, 3, 5]


You can also use various methods


```python
a.sort()
print(a)
a.append(10)
print(a)
a.reverse()
print(a)
print(type(a))
```

    [1, 2, 3, 4, 5, 10, 10]
    [1, 2, 3, 4, 5, 10, 10, 10]
    [10, 10, 10, 5, 4, 3, 2, 1]
    <class 'list'>


You can also use built-in functions


```python
print(min(a))
print(max(a))
print(sum(a))
```

    1
    10
    45


You can also add different data types


```python
a[0] = 'misl'
print(a)
min(a)
```

    ['misl', 10, 10, 5, 4, 3, 2, 1]



    

    TypeErrorTraceback (most recent call last)

    <ipython-input-14-3dfe3fa9edd5> in <module>
          1 a[0] = 'misl'
          2 print(a)
    ----> 3 min(a)
    

    TypeError: unorderable types: int() < str()


### 3) Tuples

Very similar with list, but static and fast.
You cannot modify tuples


```python
a = (5, 2, 1, 3, 4)
print(a)
print(len(a))
```

    (5, 2, 1, 3, 4)
    5



```python
print(a[0])
print(a[:3]) #from 0 to 3, but not including 3
```

    5
    (5, 2, 1)


You can assign multiple variables using tuple.


```python
(x, y) = (1, 2)
print(x)
```

    1



```python
(x, y) = (1, (2, 3))
print(y)
```

    (2, 3)



```python
(x, (y, z)) = (1, (2, 3))
print(y)
```

    2


You can omit the parenthesis


```python
lab, univ = 'misl', 'skku'
print(lab,univ)
```

    misl skku


### 4) Dictionary

It has key and value pairs. It uses hash table. It is fast


```python
info1 = {'lab':'misl', 'univ':'skku'}
print(info1)
print(info1['lab'])
```

    {'univ': 'skku', 'lab': 'misl'}
    misl



```python
info2 = {}
info2['lab'] = 'misl'
info2['univ'] = 'skku'
info2['people'] = 6
print(info2)
```

    {'univ': 'skku', 'people': 6, 'lab': 'misl'}


## 3. if, for statements


```python
iter = [3, 2, 1, 4]
for i in iter :
    print(i)
```

    3
    2
    1
    4



```python
iter = ['a', 'b', 1, 'd']
for i in iter :
    print(i)
```

    a
    b
    1
    d



```python
for i in range(5) :
    print(i)
```

    0
    1
    2
    3
    4



```python
iter = range(5)
for i in iter :
    if i is not 2 :
        print(i)
```

    0
    1
    3
    4



```python
search_list = ['banana', 'apple']
name_list = ['apple', 'banana', 'tomato']
for i in name_list :
    print(i)
    if i in search_list :
        print('Found it!\n')
```

    apple
    Found it!
    
    banana
    Found it!
    
    tomato


## 4. Numpy

Matrix operation Library

Let's solve Ax=b


```python
import numpy as np
```


```python

#Let's solve Ax=b

A = np.random.rand(10,3)
x = np.random.rand(3,1)

print(A.shape, x.shape)
print(x)
```

    (10, 3) (3, 1)
    [[0.10981214]
     [0.94816746]
     [0.09489207]]



```python
# Matrix multiplication using Numpy
b = np.matmul(A,x)
print(b)
```

    [[0.21314426]
     [0.70476535]
     [0.7688854 ]
     [0.44187604]
     [0.45944173]
     [0.7612673 ]
     [0.73500111]
     [0.27282766]
     [0.79911001]
     [0.96380795]]



```python
# Element-wise multiplication using Numpy
aa = np.ones([10,10])
bb = np.arange(10)
print(aa.shape, bb.shape)
print('aa = ',aa)
print('bb = ',bb)
print('result = ', aa*bb)
```

    (10, 10) (10,)
    aa =  [[1. 1. 1. 1. 1. 1. 1. 1. 1. 1.]
     [1. 1. 1. 1. 1. 1. 1. 1. 1. 1.]
     [1. 1. 1. 1. 1. 1. 1. 1. 1. 1.]
     [1. 1. 1. 1. 1. 1. 1. 1. 1. 1.]
     [1. 1. 1. 1. 1. 1. 1. 1. 1. 1.]
     [1. 1. 1. 1. 1. 1. 1. 1. 1. 1.]
     [1. 1. 1. 1. 1. 1. 1. 1. 1. 1.]
     [1. 1. 1. 1. 1. 1. 1. 1. 1. 1.]
     [1. 1. 1. 1. 1. 1. 1. 1. 1. 1.]
     [1. 1. 1. 1. 1. 1. 1. 1. 1. 1.]]
    bb =  [0 1 2 3 4 5 6 7 8 9]
    result =  [[0. 1. 2. 3. 4. 5. 6. 7. 8. 9.]
     [0. 1. 2. 3. 4. 5. 6. 7. 8. 9.]
     [0. 1. 2. 3. 4. 5. 6. 7. 8. 9.]
     [0. 1. 2. 3. 4. 5. 6. 7. 8. 9.]
     [0. 1. 2. 3. 4. 5. 6. 7. 8. 9.]
     [0. 1. 2. 3. 4. 5. 6. 7. 8. 9.]
     [0. 1. 2. 3. 4. 5. 6. 7. 8. 9.]
     [0. 1. 2. 3. 4. 5. 6. 7. 8. 9.]
     [0. 1. 2. 3. 4. 5. 6. 7. 8. 9.]
     [0. 1. 2. 3. 4. 5. 6. 7. 8. 9.]]



```python
# Psuedo inverse using numpy
A_pinv = np.linalg.pinv(A)
x = np.matmul(A_pinv,b)

print(x)
```

    [[0.10981214]
     [0.94816746]
     [0.09489207]]



```python

```
