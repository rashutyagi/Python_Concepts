

## Basic OOP Concepts in Python.


```python
#creating class
class Student:  # a class can never be left empty.
    pass
```


```python
#creating object of Student class
s1 = Student()
```


```python
s1
```




    <__main__.Student at 0x217afe7c0f0>




```python
type(s1)
```




    __main__.Student




```python
print(type(s1))
```

    <class '__main__.Student'>
    


```python
print(s1)
```

    <__main__.Student object at 0x00000217AFE7C0F0>
    


```python
l = list() # list is also a class
print(type(l))
```

    <class 'list'>
    


```python
s2 = Student()
s3 = Student()
print(s2, s3)
```

    <__main__.Student object at 0x00000217AE5C2CC0> <__main__.Student object at 0x00000217AE5C2B00>
    


```python
#adding data into our objects

class Student():
    pass
```


```python
s1 = Student()
s1.name = "Rashu"
```


```python
s2 = Student()
s2.roll_number = 15
```


```python
s3 = Student()
s3.name = "Rahul"
s3.roll_number = 16
```


```python
s1.name
```




    'Rashu'




```python
s2.roll_number
```




    15




```python
s3.name
```




    'Rahul'




```python
s3.roll_number
```




    16




```python
s1.roll_number
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-17-5c73248fef98> in <module>
    ----> 1 s1.roll_number
    

    AttributeError: 'Student' object has no attribute 'roll_number'



```python
s2.name
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-18-709594944e69> in <module>
    ----> 1 s2.name
    

    AttributeError: 'Student' object has no attribute 'name'



```python
#method to get all the attributes of an object
s1.__dict__
```




    {'name': 'Rashu'}




```python
s2.__dict__
```




    {'roll_number': 15}




```python
s3.__dict__
```




    {'name': 'Rahul', 'roll_number': 16}




```python
# add value to object ---> object.key = value
```


```python
#check if object has this attribute

hasattr(s1,"name")
```




    True




```python
hasattr(s1,"roll_number")
```




    False




```python
hasattr(s3,"roll_number")
```




    True




```python
# to get the value of the attribute of an object

getattr(s1,"name")
```




    'Rashu'




```python
getattr(s2,"roll_number")
```




    15




```python
getattr(s1,"roll_number")
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-30-846704dee88c> in <module>
    ----> 1 getattr(s1,"roll_number")
    

    AttributeError: 'Student' object has no attribute 'roll_number'



```python
getattr(s3,"name")
```




    'Rahul'




```python
# we can pass a third argument in getattr which will have the default value if that object has no attribute

getattr(s1,"roll_number",25)  # will happen temporarily only here.
```




    25




```python
getattr(s1,"roll_number")
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-34-846704dee88c> in <module>
    ----> 1 getattr(s1,"roll_number")
    

    AttributeError: 'Student' object has no attribute 'roll_number'



```python
getattr(s2,"roll_number",25)  # 25 is just a defalut argument.
```




    15




```python
# deleting attribute from object

delattr(s1,"name")
s1.__dict__
```




    {}



### In general above functions won't be used much because we will define what all set of attributes should our object have but it is still good to know about them.


```python
# class attribute vs object attribute.
class Student():
    passing_percent = 80 # class attribute
s1 = Student()
s2 = Student()
s1.name = "Rashu" # object attribute
s2.age = 23 #object attribute
# print(s1.__dict__)
# print(s2.__dict__)
print(s1.passing_percent,s1.name)
print(s2.passing_percent,s2.age)
```

    80 Rashu
    80 23
    


```python
s1 = Student()
s2 = Student()
s1.passing_percent = 70 # this instance attribute or object attribute will be given more preference than class attribute
print(s1.passing_percent,s2.passing_percent)
```

    70 80
    


```python
#self parameter 

class Student():
    def studentDetails():
        pass
    
s1 = Student()
s1.studentDetails()
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-43-7e02e3f0dfea> in <module>
          6 
          7 s1 = Student()
    ----> 8 s1.studentDetails()
    

    TypeError: studentDetails() takes 0 positional arguments but 1 was given


#### So we can see that above we get the error as --> studentDetails() takes 0 positional arguments but 1 was given

#### Actually this "s1.studentDetails()" is being called as "Student.studentDetails(s1)"  inside python hence it means that it is passing the object to the above function but our function is not accepting the value.


```python
# this --> "s1.studentDetails()" and this --> "Student.studentDetails(s1)"  are same
```


```python
# bydefault object is named as self

class Student():
    def studentDetails(self):
        self.name = "Rashu" # object attribute or instance attribute.
        print("name = ", self.name)
s1 = Student()
s1.studentDetails()
```

    name =  Rashu
    


```python
class Student():
    def studentDetails(self):
        self.name = "Rashu" # object attribute or instance attribute.
        print("name = ", self.name)
s1 = Student()
Student.studentDetails(s1)  #class_name.function(object_name)
```

    name =  Rashu
    

Hence we can see above that both the statements are doing the same work only hence they are same.


```python
class Student():
    def studentDetails(self):
        self.name = "Rashu" # object attribute or instance attribute. --> it is accessible till the life of this object in self
        print("name = ", self.name)
        percentage = 90 # this is a function attribute it will be accessible everytime we go inside this function
                        # this percentage is local to this function only
        print("percentage = ", percentage)
s1 = Student()
s1.studentDetails()
```

    name =  Rashu
    percentage =  90
    


```python
class Student():
    passingPercentage = 40
    
    def studentDetails(self):
        self.name = "Rashu" # object attribute or instance attribute. --> it is accessible till the life of this object in self
        print("name = ", self.name)
        percentage = 90 # this is a function attribute it will be accessible everytime we go inside this function
                        # this percentage is local to this function only
        print("percentage = ", percentage)
    def isPassed(self):
        if percentage > Student.passingPercentage: # because passing percentage is a Class attribute
                                                   # Notice here that percentage is actually local to srudentDetails function
                                                   # still we are trying to access it hence we must get error
                                                   # see the error below
            print("yes you passed")
        else:
            print("Sorry you failed")
        
s1 = Student()
s1.studentDetails()
s1.isPassed()
```

    name =  Rashu
    percentage =  90
    


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-9-3046eb8ce3dd> in <module>
         18 s1 = Student()
         19 s1.studentDetails()
    ---> 20 s1.isPassed()
    

    <ipython-input-9-3046eb8ce3dd> in isPassed(self)
          9         print("percentage = ", percentage)
         10     def isPassed(self):
    ---> 11         if percentage > Student.passingPercentage: # because passing percentage is a Class attribute
         12                                                    # Notice here that percentage is actually local to srudentDetails function
         13                                                    # still we are trying to access it hence we must get error
    

    NameError: name 'percentage' is not defined



```python
class Student():
    passingPercentage = 40
    
    def studentDetails(self):  # self acts like the object whic has been created that is passed throufh self.
        self.name = "Rashu" # object attribute or instance attribute. --> it is accessible till the life of this object in self
        print("name = ", self.name)
        self.percentage = 90 # object attribute or instance attribute. --> it is accessible till the life of this object in self
        print("percentage = ", self.percentage)
        
        
    def isPassed(self):
        if self.percentage > Student.passingPercentage:                                        
            print("yes you passed")
        else:
            print("Sorry you failed")
        
s1 = Student()
s1.studentDetails()
s1.isPassed()
```

    name =  Rashu
    percentage =  90
    yes you passed
    

### Instance methods are the methods in which "self" will be passed amd we can say that Instance methods require the default "self" whereas "static methods" do not require any self. Static methods are also called as class methods due to this property.


```python
# this code will show error 

class Student():
    passingPercentage = 40
    
    def studentDetails(self):
        self.name = "Rashu" # object attribute or instance attribute. --> it is accessible till the life of this object in self
        print("name = ", self.name)
        self.percentage = 90 # object attribute or instance attribute. --> it is accessible till the life of this object in self
        print("percentage = ", self.percentage)
        
        
    def isPassed(self):
        if self.percentage > Student.passingPercentage:                                        
            print("yes you passed")
        else:
            print("Sorry you failed")
            
    def welcomeToSchool(): # now we dont want this method to be attached to self as it has nothing to do with any student it 
                           # is for entire school.
        print("Heyy!! Welcome to the School Buddy")
        
s1 = Student()
s1.studentDetails()
s1.isPassed()
s1.welcomeToSchool()
```

    name =  Rashu
    percentage =  90
    yes you passed
    


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-13-5d9716b092d1> in <module>
         24 s1.studentDetails()
         25 s1.isPassed()
    ---> 26 s1.welcomeToSchool()
    

    TypeError: welcomeToSchool() takes 0 positional arguments but 1 was given



```python
# this is how you remove the attachment of self from any method

class Student():
    passingPercentage = 40
    
    def studentDetails(self):
        self.name = "Rashu" # object attribute or instance attribute. --> it is accessible till the life of this object in self
        print("name = ", self.name)
        self.percentage = 90 # object attribute or instance attribute. --> it is accessible till the life of this object in self
        print("percentage = ", self.percentage)
        
        
    def isPassed(self):
        if self.percentage > Student.passingPercentage:                                        
            print("yes you passed")
        else:
            print("Sorry you failed")
            
    @staticmethod   # now this method will not demand for "self" parameter  ---> This is called as Decorator.    
    def welcomeToSchool(): # now we dont want this method to be attached to self as it has nothing to do with any student it 
                           # is for entire school.
        print("Heyy!! Welcome to the School Buddy")
        
s1 = Student()
s1.studentDetails()
s1.isPassed()
s1.welcomeToSchool()
```

    name =  Rashu
    percentage =  90
    yes you passed
    Heyy!! Welcome to the School Buddy
    


```python
# init method

class Student:
    def __init__(self):        # self has the address of the object which has been created in our case self and s1 have
        self.name = "Rashu"    # same reference.
        self.rollNumber = 15 
                      

    
```


```python
s1 = Student() # __init__() function is called in the class as soon as we create an object of that class.
s1.__dict__


```




    {'name': 'Rashu', 'rollNumber': 15}




```python
s2 = Student()
s2.__dict__
```




    {'name': 'Rashu', 'rollNumber': 15}



### But we would want to give different name and roll number to different students (objects)


```python
# init method

class Student:
    def __init__(self,name,rollNumber):        # self has the address of the object which has been created in our case 
        self.name = name                       # self and s1 have same reference.
        self.rollNumber = rollNumber 
                      

    
```


```python
s3 = Student("Rashu",15)
s3.__dict__
```




    {'name': 'Rashu', 'rollNumber': 15}



### Factory methods --> when we need to return the object of the class. We use @classmethod as decorator for them.  For them first argument must be class name.


```python
from datetime import date



class Student():
    passingPercentage = 40
    
    def __init__(self, name, age = 15, percentage = 80):
        self.name = name
        self.age = age
        self.percentage = percentage
    
    def studentDetails(self):
        self.name = "Rashu" # object attribute or instance attribute. --> it is accessible till the life of this object in self
        print("name = ", self.name)
        self.percentage = 90 # object attribute or instance attribute. --> it is accessible till the life of this object in self
        print("percentage = ", self.percentage)
        
        
    def isPassed(self):
        if self.percentage > Student.passingPercentage:                                        
            print("yes you passed")
        else:
            print("Sorry you failed")
            
            
    """This type of method takes neither a self nor a cls parameter (but of course it’s free to accept an arbitrary 
       number of other parameters).
       Therefore a static method can neither modify object state nor class state.
       Static methods are restricted in what data they can access - 
       and they’re primarily a way to namespace your methods."""
            
    @staticmethod   # now this method will not demand for "self" parameter  ---> This is called as Decorator.    
    def welcomeToSchool(): # now we dont want this method to be attached to self as it has nothing to do with any student it 
                           # is for entire school.
        print("Heyy!! Welcome to the School Buddy")
        
    @staticmethod
    def isTeen(age):
        return age>16
    
    """Instead of accepting a self parameter, class methods take a cls parameter that points to the 
       class—and not the object instance—when the method is called. 
       Because the class method only has access to this cls argument, it can’t modify object instance state. 
       That would require access to self. However, class methods can still modify class state that applies 
       across all instances of the class."""
    
    @classmethod
    def fromBirthYear(cls, name, year, percentage):
        return cls(name, date.today().year - year, percentage)
    
        
s1 = Student()
s1.studentDetails()
s1.isPassed()
s1.welcomeToSchool()

```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-3-5db22455ed4b> in <module>
         51 
         52 
    ---> 53 s1 = Student()
         54 s1.studentDetails()
         55 s1.isPassed()
    

    TypeError: __init__() missing 1 required positional argument: 'name'



```python

```


```python
from datetime import date



class Student():
    passingPercentage = 40
    
    def __init__(self, name, age = 15, percentage = 80):
        self.name = name
        self.age = age
        self.percentage = percentage
    
    def studentDetails(self):
        self.name = "Rashu" # object attribute or instance attribute. --> it is accessible till the life of this object in self
        print("name = ", self.name)
        self.percentage = 90 # object attribute or instance attribute. --> it is accessible till the life of this object in self
        print("percentage = ", self.percentage)
        
        
    def isPassed(self):
        if self.percentage > Student.passingPercentage:                                        
            print("yes you passed")
        else:
            print("Sorry you failed")
            
            
    """This type of method takes neither a self nor a cls parameter (but of course it’s free to accept an arbitrary 
       number of other parameters).
       Therefore a static method can neither modify object state nor class state.
       Static methods are restricted in what data they can access - 
       and they’re primarily a way to namespace your methods."""
            
    @staticmethod   # now this method will not demand for "self" parameter  ---> This is called as Decorator.    
    def welcomeToSchool(): # now we dont want this method to be attached to self as it has nothing to do with any student it 
                           # is for entire school.
        print("Heyy!! Welcome to the School Buddy")
        
    @staticmethod
    def isTeen(age):
        return age>16
    
    """Instead of accepting a self parameter, class methods take a cls parameter that points to the 
       class—and not the object instance—when the method is called. 
       Because the class method only has access to this cls argument, it can’t modify object instance state. 
       That would require access to self. However, class methods can still modify class state that applies 
       across all instances of the class."""
    
    @classmethod
    def fromBirthYear(cls, name, year, percentage):
        return cls(name, date.today().year - year, percentage)
    
        
```


```python
s1 = Student("Rashu")
print(s1.name)
```

    Rashu
    


```python
# we can change this name from outside as well 

s1.name = "Vashu"
print(s1.name)  # hence nothing is private right now.
```

    Vashu
    


```python
s1 = Student("Rashu")
print(s1.name,s1.age)
```

    Rashu 15
    


```python
s1.name = "Vashu"
s1.age = 20
print(s1.name,s1.age) # see again that nothing is private right now.
```

    Vashu 20
    

#### name and age were public right now.

We can make the following changes <br>
By adding __ before the variable name we make it private


```python
from datetime import date



class Student():
    passingPercentage = 40
    
    def __init__(self, name, age = 15, percentage = 80):
        self.__name = name
        self.age = age
        self.percentage = percentage
    
    def studentDetails(self):
        self.name = "Rashu" # object attribute or instance attribute. --> it is accessible till the life of this object in self
        print("name = ", self.name)
        self.percentage = 90 # object attribute or instance attribute. --> it is accessible till the life of this object in self
        print("percentage = ", self.percentage)
        
        
    def isPassed(self):
        if self.percentage > Student.passingPercentage:                                        
            print("yes you passed")
        else:
            print("Sorry you failed")
            
            
    """This type of method takes neither a self nor a cls parameter (but of course it’s free to accept an arbitrary 
       number of other parameters).
       Therefore a static method can neither modify object state nor class state.
       Static methods are restricted in what data they can access - 
       and they’re primarily a way to namespace your methods."""
            
    @staticmethod   # now this method will not demand for "self" parameter  ---> This is called as Decorator.    
    def welcomeToSchool(): # now we dont want this method to be attached to self as it has nothing to do with any student it 
                           # is for entire school.
        print("Heyy!! Welcome to the School Buddy")
        
    @staticmethod
    def isTeen(age):
        return age>16
    
    """Instead of accepting a self parameter, class methods take a cls parameter that points to the 
       class—and not the object instance—when the method is called. 
       Because the class method only has access to this cls argument, it can’t modify object instance state. 
       That would require access to self. However, class methods can still modify class state that applies 
       across all instances of the class."""
    
    @classmethod
    def fromBirthYear(cls, name, year, percentage):
        return cls(name, date.today().year - year, percentage)
    
        
```


```python
s1 = Student("Rashu")
print(s1.name) # we wont be able to access it
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-12-d9bd92f3ed43> in <module>
          1 s1 = Student("Rashu")
    ----> 2 print(s1.name) # we wont be able to access it
    

    AttributeError: 'Student' object has no attribute 'name'



```python
s1 = Student("Rashu")
print(s1.__name) # we wont be able to access it
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-13-1d0006b21414> in <module>
          1 s1 = Student("Rashu")
    ----> 2 print(s1.__name) # we wont be able to access it
    

    AttributeError: 'Student' object has no attribute '__name'


#### __name is nothing outside the class but insdie the class it can be changed see the code below


```python
from datetime import date



class Student():
    passingPercentage = 40
    
    def __init__(self, name, age = 15, percentage = 80):
        self.__name = name
        self.age = age
        self.percentage = percentage
    
    def studentDetails(self):
        self.name = "Rashu" # object attribute or instance attribute. --> it is accessible till the life of this object in self
        print("name = ", self.__name) # trying to access the private variable inside the class.
        self.percentage = 90 # object attribute or instance attribute. --> it is accessible till the life of this object in self
        print("percentage = ", self.percentage)
        
        
    def isPassed(self):
        if self.percentage > Student.passingPercentage:                                        
            print("yes you passed")
        else:
            print("Sorry you failed")
            
            
    """This type of method takes neither a self nor a cls parameter (but of course it’s free to accept an arbitrary 
       number of other parameters).
       Therefore a static method can neither modify object state nor class state.
       Static methods are restricted in what data they can access - 
       and they’re primarily a way to namespace your methods."""
            
    @staticmethod   # now this method will not demand for "self" parameter  ---> This is called as Decorator.    
    def welcomeToSchool(): # now we dont want this method to be attached to self as it has nothing to do with any student it 
                           # is for entire school.
        print("Heyy!! Welcome to the School Buddy")
        
    @staticmethod
    def isTeen(age):
        return age>16
    
    """Instead of accepting a self parameter, class methods take a cls parameter that points to the 
       class—and not the object instance—when the method is called. 
       Because the class method only has access to this cls argument, it can’t modify object instance state. 
       That would require access to self. However, class methods can still modify class state that applies 
       across all instances of the class."""
    
    @classmethod
    def fromBirthYear(cls, name, year, percentage):
        return cls(name, date.today().year - year, percentage)
    
        
```


```python
s1 = Student("Rashu")
#print(s1.name) # we wont be able to access it
s1.studentDetails()  # here we are still able to access the __name as it was inside the class
```

    name =  Rashu
    percentage =  90
    

### Python uses the concept of name mangling.

object.__variable --> object._Classname__variablename


```python
from datetime import date



class Student():
    passingPercentage = 40
    
    def __init__(self, name, age = 15, percentage = 80):
        self.__name = name
        self.age = age
        self.percentage = percentage
    
    def studentDetails(self):
        self.name = "Rashu" # object attribute or instance attribute. --> it is accessible till the life of this object in self
        print("name = ", self.__name) # trying to access the private variable inside the class.
        self.percentage = 90 # object attribute or instance attribute. --> it is accessible till the life of this object in self
        print("percentage = ", self.percentage)
        
        
    def isPassed(self):
        if self.percentage > Student.passingPercentage:                                        
            print("yes you passed")
        else:
            print("Sorry you failed")
            
            
    """This type of method takes neither a self nor a cls parameter (but of course it’s free to accept an arbitrary 
       number of other parameters).
       Therefore a static method can neither modify object state nor class state.
       Static methods are restricted in what data they can access - 
       and they’re primarily a way to namespace your methods."""
            
    @staticmethod   # now this method will not demand for "self" parameter  ---> This is called as Decorator.    
    def welcomeToSchool(): # now we dont want this method to be attached to self as it has nothing to do with any student it 
                           # is for entire school.
        print("Heyy!! Welcome to the School Buddy")
        
    @staticmethod
    def isTeen(age):
        return age>16
    
    """Instead of accepting a self parameter, class methods take a cls parameter that points to the 
       class—and not the object instance—when the method is called. 
       Because the class method only has access to this cls argument, it can’t modify object instance state. 
       That would require access to self. However, class methods can still modify class state that applies 
       across all instances of the class."""
    
    @classmethod
    def fromBirthYear(cls, name, year, percentage):
        return cls(name, date.today().year - year, percentage)
    
        
```


```python
s1 = Student("Rashu")
print(s1._Student__name) # using this we can access the private members also but it is not our responsibility to not do this.
```

    Rashu
    

### So actually Python has no concept of Private they can still be accessed but we shoould not do that as developers.

## Class variable can also be made private variable


```python
from datetime import date



class Student():
    __passingPercentage = 40
    
    def __init__(self, name, age = 15, percentage = 80):
        self.__name = name
        self.age = age
        self.percentage = percentage
    
    def studentDetails(self):
        self.name = "Rashu" # object attribute or instance attribute. --> it is accessible till the life of this object in self
        print("name = ", self.__name) # trying to access the private variable inside the class.
        self.percentage = 90 # object attribute or instance attribute. --> it is accessible till the life of this object in self
        print("percentage = ", self.percentage)
        
        
    def isPassed(self):
        if self.percentage > Student.passingPercentage:                                        
            print("yes you passed")
        else:
            print("Sorry you failed")
            
            
    """This type of method takes neither a self nor a cls parameter (but of course it’s free to accept an arbitrary 
       number of other parameters).
       Therefore a static method can neither modify object state nor class state.
       Static methods are restricted in what data they can access - 
       and they’re primarily a way to namespace your methods."""
            
    @staticmethod   # now this method will not demand for "self" parameter  ---> This is called as Decorator.    
    def welcomeToSchool(): # now we dont want this method to be attached to self as it has nothing to do with any student it 
                           # is for entire school.
        print("Heyy!! Welcome to the School Buddy")
        
    @staticmethod
    def isTeen(age):
        return age>16
    
    """Instead of accepting a self parameter, class methods take a cls parameter that points to the 
       class—and not the object instance—when the method is called. 
       Because the class method only has access to this cls argument, it can’t modify object instance state. 
       That would require access to self. However, class methods can still modify class state that applies 
       across all instances of the class."""
    
    @classmethod
    def fromBirthYear(cls, name, year, percentage):
        return cls(name, date.today().year - year, percentage)
    
        
```


```python
s1 = Student("Rashu")
print(s1.passingPercentage) # see we can not access a private class variable also.
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-23-27de8407f8fa> in <module>
          1 s1 = Student("Rashu")
    ----> 2 print(s1.passingPercentage)
    

    AttributeError: 'Student' object has no attribute 'passingPercentage'



```python
s1 = Student("Rashu")
print(s1.__passingPercentage)
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-24-89f9c5e0f5dc> in <module>
          1 s1 = Student("Rashu")
    ----> 2 print(s1.__passingPercentage)
    

    AttributeError: 'Student' object has no attribute '__passingPercentage'



```python
s1 = Student("Rashu")
print(s1._Student__passingPercentage) # this way you can access the private variables but you should not.
```

    40
    


```python

```
