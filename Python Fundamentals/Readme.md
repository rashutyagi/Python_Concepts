
# PYTHON

## Introduction 

Python is a programmer friendly High Level Programming Level.
Python is a general purpose high level programming language.
Python was created by Guido Van Rossum.


Java came in 1995 while Python came in 1991

For all the new trending requirement Python is the best suitable programming language

The below code can be understood by a kid also and this much simple is python code.


```python
a = 5 
b = 10
c = a + b
print(c)
```

    15
    

C - Functional Programming Language <br>
C++,Java - Object Oriented Programming Language <br>
Perl,Shell Script - Scripting language (Everything is executed line by line) <br>
Modula-3 - Modular Programming Langauge <br>
Python - "Has all the above features"


In python there are only 33 keywords hence we say that it is easier to learn and simple to understand.

Python code is very much concise to write. Example - 


```python
# using the below single line code you can read data from file "abc.txt" and print it also.
print(open("abc.txt").read())
```

Platform specific PVM are present hence we can say that python is a portable language. Python Application is platform independent while PVM is platform specific which converts the Python Application code into the required form by specific system like Windows,Linux,Mac etc

Python is Dynamically typed language and by that we mean to say that we don't need to declare the type of the variables because it is detected automatically by the interpreter Example -


```python
a = 10
print(type(a))
```

    <class 'int'>
    


```python
a = 10.5
print(type(a))
```

    <class 'float'>
    


```python
a = "Hello World"
print(type(a))
```

    <class 'str'>
    

Python is both Proceure and Object Oriented Python Language along with being a scripting langauge and modular programming language.

Python programs don't need to be compiled explicitly rather they are interpretted automatically.

Python has great support of many libraries.

### Limitations of Python

There are some limitations for python language also <br>
Python is not suitable for developing Mobile Applications till now as there is no library support for mobile applications<br>
Python not suitable for Enterprise Applications <br>
Performance wise python is not that good because it is interpretted in nature <br>
To improve this people have added JIT compiler that version is called as pypy(python for speed).



### Versions of Python

Due to Python being open source there are many versions of python possible :- <br>
Cpython <br>
Jpython/Jython <br>
Iron Python <br>
Ruby Python <br>
Anaconda Python <br>
Stackless(Python for concurrency) <br>
pypy(python for speed,it contains JIT compiler which stands for just in time compiler).


```python

```

# Fundamentals of Python Programming

### Python Identifiers

A name in python program is called as identifier.It can be a variable name or class name or method name etc <br>
There are some rules regarding identifiers in python and they are like : <br>
1.) Only allowed symbols are a-z,A-Z,0 to 9,_ (underscore) <br>
2.) You cannot start an identifier with a digit <br>
3.) Python is case sensitive language. <br>
4.) There is no limit on the length of the variable in python.(not recommended t otake long identifiers) <br>
5.) Keywords can not be used a identifiers

    


```python
rashu = 10 #valid
```


```python
ra&hu = 10 #invalid
```


      File "<ipython-input-2-e3b13ea48152>", line 1
        ra&hu = 10 #invalid
                           ^
    SyntaxError: can't assign to operator
    



```python
abc123 = 20 #valid
```


```python
123abc = 55 #invalid
```


      File "<ipython-input-4-e5c61bbbe08e>", line 1
        123abc = 55 #invalid
             ^
    SyntaxError: invalid syntax
    



```python
abc = 10
```


```python
Abc = 20
```


```python
ABC = 30
```


```python
print(abc,Abc,ABC)
```

    10 20 30
    


```python
if = 10 # invalid as if is a keyword
```


      File "<ipython-input-10-8eafb90ec5c0>", line 1
        if = 10 # invalid as if is a keyword
           ^
    SyntaxError: invalid syntax
    


### Story of types of variables 


```python
x = 10 # means x is a normal variable 
```


```python
_x = 10 # menas x is a protected variable
```


```python
__x = 10 # means x is a private variable
```


```python
__x__ = 10 # means x is a magic variable
```

All the above are language specific variables

## Reserved Words (Keywords)

There are 33 keywords in python and they represent some meaning or functionality and they are : <br>
True,False,None <br>
and , or , not , is <br>
if , elif , else <br>
while , for , break , continue , return , in , yield <br>
try , except , finally , raise , assert <br>
import , from , as , class , def , pass <br>
global , nonlocal , lambda , del , with <br>


```python
true = 10 #valid
```


```python
True = 10 #invalid
```


      File "<ipython-input-17-9268142eb66c>", line 1
        True = 10 #invalid
                          ^
    SyntaxError: can't assign to keyword
    



```python
false =20 #valid
```


```python
False = 20 # invalid
```


      File "<ipython-input-19-c369f5a312e2>", line 1
        False = 20 # invalid
                            ^
    SyntaxError: can't assign to keyword
    


Switch , do-while concepts are not there in python also names like int,float etc are not the keywords in python


```python
import keyword
print("Following are all the keywords in python")
for i in keyword.kwlist:
    print(i)
print ("Total number of keywords are " , len(keyword.kwlist))
```

    Following are all the keywords in python
    False
    None
    True
    and
    as
    assert
    async
    await
    break
    class
    continue
    def
    del
    elif
    else
    except
    finally
    for
    from
    global
    if
    import
    in
    is
    lambda
    nonlocal
    not
    or
    pass
    raise
    return
    try
    while
    with
    yield
    Total number of keywords are  35
    

## Data Types

It tells us the type of data stored in our variables. <br>
Python is dynamically typed programming language in this the type is detected automatically


```python
a = 10
print(type(a))
b  = 10.6
print(type(b))
c = True
print(type(c))
```

    <class 'int'>
    <class 'float'>
    <class 'bool'>
    

Availiable data types in python are : int,float,complex,bool,str,list,tuple,set,frozenset,dict,bytes,bytearray,range,None.(14 data types in python)

##### Everything in python is an object


```python
a = 10 # means a is an object only pointing to value 10 
```


```python
id(a) # we get the address of a 
```




    140704548361312



We do not have long data type in Python 3 it was only in Python 2 


```python
a = 178347685476887453287438793489489489432
```


```python
type(a)
```




    int



Binary vs Decimal representation


```python
a = 1111 #default is decimal representation
a
```




    1111




```python
a = 0B1111 #using 0B in the start gives us the Binary Representation
a
```




    15




```python
a = 0b1111 #using 0b in the start also gives us the Binary Representation
a
```




    15




```python
#octal form 
a = 0o123
a
```




    83




```python
a = 0O123
a
```




    83



Keep in mind that in octal numbers representation we can not use any number out of the range 0-7


```python
#Hexadecimal form
a = 0x10
a
```




    16




```python
a = 0X01
a
```




    1




```python
a = 0xFace
a
```




    64206



Keep in mind that in hexadecimal the digits allowed are from 0 to 9,A-F,a-f, you can use uppercase or lower case it does not matter here.

#### Python always gives output always in decimal form by default

Now in order to convert the number returned by python in decimal form to any other form we use base conversion functions like this :


```python
a = bin(15) # bin() function gives the binary representation
a
```




    '0b1111'




```python
a = bin(0o123)
a
```




    '0b1010011'




```python
a = oct(100) # oct() function gives the octal representation
a
```




    '0o144'




```python
a = oct(0b1111010011)
a
```




    '0o1723'




```python
a = hex(1000)
a
```




    '0x3e8'




```python
a = hex(0b1101000101)
a
```




    '0x345'



##### Float Data Type


```python
a = 1.345
type(a)
```




    float



## Float type values can be represented only in the decimal form and not in binary or octal or hexadecimal form.


```python
f = 1.2e3 #exponentail form or scientific notation form -> 1.2 * 10^3
f
```




    1200.0




```python
f = 1.2E3
f
```




    1200.0



#### Complex data type


```python
x = 10 + 7j
type(x)
```




    complex




```python
x = 10 + 7i
type(x)
```


      File "<ipython-input-48-6ed1215710ae>", line 1
        x = 10 + 7i
                  ^
    SyntaxError: invalid syntax
    



```python
x = 10 + 7j
print(x.real)
```

    10.0
    


```python
x = 10 + 7j
print(x.imag)
```

    7.0
    

Real part can be represented in any form but imaginary part can be specified in decimal form only

#### Boolean Data Type


```python
a = True
b = False
print(type(a))
print(type(b))
```

    <class 'bool'>
    <class 'bool'>
    

Internally True means 1 and False is represented as 0


```python
print(True + True)
print(True - True)
print(True + False)
print(True * False)
```

    2
    0
    1
    0
    

#### String Data Type


```python
#both single and double quotes work perfectly for strings
a = 'Rashu'
b = "Rashu"
print(a)
print(b)
```

    Rashu
    Rashu
    


```python
type('a') # In python there is no char data type
```




    str




```python
# we can use triple quotes also in python for strings
a = """Rashu"""
a
```




    'Rashu'




```python
type(a)
```




    str




```python
#multiline string literals are not su[[ported by single or double quotes but are applied with triple quotes
a = "Python 
    is a good
     language"
```


      File "<ipython-input-7-b403ea42e299>", line 1
        a = "Python
                    ^
    SyntaxError: EOL while scanning string literal
    



```python
a = 'Python 
    is a good
     language'
```


      File "<ipython-input-8-4bc3ad7aefa5>", line 1
        a = 'Python
                    ^
    SyntaxError: EOL while scanning string literal
    



```python
a = """Python 
    is a good
     language"""
a
```




    'Python \n    is a good\n     language'




```python
#suppose we want to print something with double quotes and triple quotes then we will need to use triple quotes

a = "Hey 'hi' how are you"
print(a)
b = 'Hey "hi" how are you'
print(b)
c = """hey hi 'how' are "you" """
print(c)
```

    Hey 'hi' how are you
    Hey "hi" how are you
    hey hi 'how' are "you" 
    

We use triple quotes also to define the documentation Strings

Index speciality is also there in the strings in python.


```python
s = "Rashu"
s[0]
```




    'R'




```python
s[4]
```




    'u'




```python
s[10]
```


    ---------------------------------------------------------------------------

    IndexError                                Traceback (most recent call last)

    <ipython-input-14-34c622ab6870> in <module>
    ----> 1 s[10]
    

    IndexError: string index out of range



```python
s[-1]
```




    'u'




```python
s[-3]
```




    's'



#### Python provides support for both positive and negative indexes. Keep in mind that negative indexes start the characters from the end.

There is concept of slicing also in python for strings


```python
#Slice operator in python --> s[begin index : end] --> returns a substring from begin index to end - 1 index.

s = "Hello to the world of Python"
s[3:9]
```




    'lo to '




```python
s[:8] # will start from the 0th index
```




    'Hello to'




```python
s[3:] # will go till the end
```




    'lo to the world of Python'




```python
s[2:2000] # you will not get index error in slice operator
```




    'llo to the world of Python'




```python
s[10:3] # no slicing possible here
```




    ''




```python
a = "rashu"
out = a[0].upper() + a[1:]
out
```




    'Rashu'




```python
a = "rashu"
out = a[:len(a) - 1] + a[-1].upper() 
out
```




    'rashU'




```python
a = "rashu"
out = a[0].upper() + a[1:len(a) - 1] + a[-1].upper() 
out
```




    'RashU'



### + Operator for String


```python
s = "Hello"  + "World" # Both arguments must be string type only always.
s
```




    'HelloWorld'




```python
s = "Hello" + 10
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-3-24afcf44e72b> in <module>
    ----> 1 s = "Hello" + 10
    

    TypeError: can only concatenate str (not "int") to str


### * Operator


```python
s = "Hello " * 3 #perfectly acceptable in python
s
```




    'Hello Hello Hello '




```python
s = 3 * "Hello" 
s
```




    'HelloHelloHello'




```python
s = "Hello" * "World" # when ever you are using * operator remember that one argument must be string and other must be integer always.
s
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-9-58fb609a3433> in <module>
    ----> 1 s = "Hello" * "World" # when ever you are using * operator remember that one argument must be string and other must be integer always.
          2 s
    

    TypeError: can't multiply sequence by non-int of type 'str'



```python

```

### Type Casting or Type Coersion


```python
# int() --> to convert from other types to int type

a = int(10.989) # digits after the decimal will be gone
a
```




    10




```python
b = int(10.24) # digits after the decimal will be gone
b
```




    10




```python
c = int(10 + 20j) # you cannot convert complex type to int type.
c
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-4-5f11a3bb7c6e> in <module>
    ----> 1 c = int(10 + 20j)
          2 c
    

    TypeError: can't convert complex to int



```python
a = int(True)
b = int(False)
print(a,b)
```

    1 0
    


```python
d = int("156") # we can convert string to int only when the string internally contains integral value that too in base 10 form.
d
```




    156




```python
d = int("156.45")
d
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-13-8afec0a97c1a> in <module>
    ----> 1 d = int("156.45")
          2 d
    

    ValueError: invalid literal for int() with base 10: '156.45'



```python
e = int("True")
e
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-7-0730ccfa91cc> in <module>
    ----> 1 e = int("True")
          2 e
    

    ValueError: invalid literal for int() with base 10: 'True'



```python
e = int("Hello")
e
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-8-e395f1e6d7d2> in <module>
    ----> 1 e = int("Hello")
          2 e
    

    ValueError: invalid literal for int() with base 10: 'Hello'



```python
e = int('0B1111') # Boolean for mnot allowed.
e
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-9-5b4579da4f28> in <module>
    ----> 1 e = int('0B1111')
          2 e
    

    ValueError: invalid literal for int() with base 10: '0B1111'



```python
a = float(15)
a
```




    15.0




```python
b = float(5 + 10j) # you can not convert complex number to float
b
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-11-c72337107512> in <module>
    ----> 1 b = float(5 + 10j) # you can not convert complex number to float
          2 b
    

    TypeError: can't convert complex to float



```python
c = float(True)
d = float(False)
print(c,d)
```

    1.0 0.0
    


```python
#internally string should contain int value or float value in base 10

c = float("10.45")
c
```




    10.45




```python
# for complex type if you pass only one value then it will become real value

d = complex(10)
d
```




    (10+0j)




```python
d = complex(0B1111)
d
```




    (15+0j)




```python
d = complex(10.5)
d
```




    (10.5+0j)




```python
d = complex(True)
d
```




    (1+0j)




```python
d = complex(False)
d
```




    0j




```python
d = complex("10.5")
d
```




    (10.5+0j)




```python
d = complex("10")
d
```




    (10+0j)




```python
d = complex("0B1111")
d
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-22-8e42a63583cd> in <module>
    ----> 1 d = complex("0B1111")
          2 d
    

    ValueError: complex() arg is a malformed string



```python
# if you pass two values then first value will become real value and second value will become imaginary value
d = complex(10.5,20.5)
d
```




    (10.5+20.5j)




```python
d = complex("10" , "20")
d
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-24-407ea18fc79b> in <module>
    ----> 1 d = complex("10" , "20")
          2 d
    

    TypeError: complex() can't take second arg if first is a string



```python
d = complex(10 , "20")
d
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-25-cc4a3633f602> in <module>
    ----> 1 d = complex(10 , "20")
          2 d
    

    TypeError: complex() second arg can't be a string



```python
d = complex("10" , 20)
d
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-26-420ce9511826> in <module>
    ----> 1 d = complex("10" , 20)
          2 d
    

    TypeError: complex() can't take second arg if first is a string



```python
d = complex("10")
d
```




    (10+0j)




```python
d = complex(10 , "20")
d
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-28-cc4a3633f602> in <module>
    ----> 1 d = complex(10 , "20")
          2 d
    

    TypeError: complex() second arg can't be a string



```python
# non zero means True and 0 means false always 

a = bool(10)
b = bool(0)
c = bool(-10)
d = bool(0.0)
e = bool(0.0001)
f = bool(-0.00021)
g = bool(0 + 0j)
h = bool(1 + 0j)
i = bool(0+5j)
print(a,b,c,d,e,f,g,h,i)
```

    True False True False True True False True True
    


```python
bool("True")
```




    True




```python
bool("False")
```




    True




```python
bool("Hey")
```




    True




```python
bool("No")
```




    True




```python
bool("") # only bool() of empty string gives us False rest all gives us True
```




    False




```python
bool(" ")
```




    True




```python
str(10)
```




    '10'




```python
str(0B1111) # output will always be in Decimal form
```




    '15'




```python
str(10.5)
```




    '10.5'




```python
str(10+20j)
```




    '(10+20j)'




```python
str(True)
```




    'True'




```python
str(False)
```




    'False'



Hece we can say that we can convert any type to string type


```python

```

### Fundamental Data Types Vs Immutability

The 5 fundamental data types are <br>
int <br>
float <br>
complex <br>
bool <br>
str <br>

And always keep in mind that all the fundamental data types are immutable(they can not be changed)

Once we create an object we cannot perform any changes in that object and if we are trying to perform any changes all those changed will be incorporated and a new object will be created with all those changes.


```python
x = 10
print(id(x))
x= x + 1
print(id(x))
```

    140711835243616
    140711835243648
    


```python
x = 10
y = 10 
print(id(x))
print(id(y)) # both will point to the same object "10" which was created.
```

    140711835243616
    140711835243616
    

### All those objects to which no one is pointing will be eligible for Garbage Collection.

Immutability concept helps in better memory utilization and hence improving the performance.


```python
# a is b operator will return true if both are poining to the same object

a = 100
b = 100

print(a is b)
```

    True
    


```python
a = True
b = True

print(a is b)
```

    True
    


```python
a = "Hey"
b = "Hey"

print(a is b)
```

    True
    


```python
a = 10.8
b = 10.8

print(a is b)
```

    False
    

### Object reusing capability is not availiable for complex data types.


```python
a = 5 + 12j
b = 5 + 12j

print(a is b)
```

    False
    

### List is mutable


```python
l = [10,20,30]
print(id(l))
print(l)
l[0] = 5458
print(id(l))
print(l)
```

    2429381368904
    [10, 20, 30]
    2429381368904
    [5458, 20, 30]
    


```python
# any changes will be replaced in the second list also as they use the concept of object reusability.
l1 = [10,20,30]
l2 = l1
print(l1)
l1[0] = 223654
print(l2)
```

    [10, 20, 30]
    [223654, 20, 30]
    

## Datatypes required for collections (to store a group of values)

All these are the data types used for the purpose of storing collections <br>
List <br>
Tuple <br>
Set <br>
frozenset <br>
dict <br>
range <br>
bytes <br>
bytearray 

## List


```python
# insertion order is important in list and duplicates are also allowed

l = [10,'rashu',35,10,234]
print(type(l))
print(l)
```

    <class 'list'>
    [10, 'rashu', 35, 10, 234]
    


```python
# indexing is applicable in Lists

print(l[0] , l[1] , l[3])
```

    10 rashu 10
    


```python
l[1:4] # slicing operator is also applicable
```




    ['rashu', 35, 10]




```python
l.append(254)
l
```




    [10, 'rashu', 35, 10, 234, 254]




```python
l.remove(35)
l
```




    [10, 'rashu', 10, 234, 254]




```python
l.remove(10) # initial 10 will be removed.
l
```




    ['rashu', 10, 234, 254]



## Tuple 

All things are same in list and tuple except the fact that tuples are immutable.Tuple are basically the read only version of List


```python
t = (10,34,21,78)
type(t)
```




    tuple



You cannot make any changes in the tuple object as it is immutable in nature. Rest all things are similar in tuple just like list. <br>
Functions like append and remove are not present fopr tuple objects.


```python
# important 

t = ()
print(type(t))
```

    <class 'tuple'>
    


```python
# it is a common practice to represent normal numbers in () that's why we get this issue.
t = (10)
print(type(t))
```

    <class 'int'>
    


```python
# single value tuple should end with comma (,)

t = (10,)
print(type(t))
```

    <class 'tuple'>
    

### Set

In case of set we need to keep in mind that inside sets order doesnot matter due to which there is no concept of indexing and in sets there are no duplicates also allowed. <br>
Also sets are growable and mutable


```python
s = {10,20,'rashu',46}
print(type(s))
```

    <class 'set'>
    


```python
s.add(50)
s
```




    {10, 20, 46, 50, 'rashu'}




```python
s.remove(46)
s
```




    {10, 20, 50, 'rashu'}




```python
s = {}
print(type(s))
```

    <class 'dict'>
    


```python
# this is how you create an empty set

s = set()
print(type(s))
```

    <class 'set'>
    

## FrozenSet 

It is exactly same as set but the only change is that it is immutable


```python
s = {10,20,'rashu',46}
fs = frozenset(s)
print(type(fs))
```

    <class 'frozenset'>
    


```python
fs.add(435)
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-18-0a8f859b3b66> in <module>
    ----> 1 fs.add(435)
    

    AttributeError: 'frozenset' object has no attribute 'add'



```python
s.add(454)
```


```python
s
```




    {10, 20, 454, 46, 'rashu'}




```python
fs.remove(10)
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-22-b658f8c94e09> in <module>
    ----> 1 fs.remove(10)
    

    AttributeError: 'frozenset' object has no attribute 'remove'



```python

```
