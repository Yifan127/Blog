### Class

#### Class Definition

```python
class Person(object):
    '''This is a simple example class'''
    count = 0

    def __init__(self, name, age):
        self.name = name
        self.age = age
        Person.count += 1

    def displayPerson(self):
        print('name: ' + self.name + ' age: ' + str(self.age))
```

#### \_\_init\_\_ and self, what do they do?

**\_\_init\_\_** is like a constructor in Python.

When a class defines an \_\_init\_\_, class instatiation automatically invokes \_\_init\_\_() for the newly-created class instance. 

**self** represents the instance of the object itself

For example, when I call Person('Mike', 22), Python creates an object, and passes it as the first paremeter to the \_\_init\_\_ method. Any additional parameters like ('Mike', 22) will also get passed as arguments.

#### Class Object: Attribute references and instantiation.
* Attribute references

```python
    Person.count
    Person.displayPerson()
```
* Instantiation

```python
    mike = Person('Mike', 22)
```    

#### Instance Object: Attribute references.
```python
    mike.count
    mike.age
    mike.displayPerson()
```

#### Class and Instance Variables

**Class variables** are for attributes and methods shared by all instances.

**Instance variables** are for data unique to each instance.

```python
class Person(object):
    '''This is a simple example class'''
    count = 0

    def __init__(self, name, age):
        self.name = name
        self.age = age
        Person.count += 1

    def displayPerson(self):
        print('name: ' + self.name + ' age: ' + str(self.age))

mike = Person('Mike', 22)
lily = Person('Lily', 25)

print(mike.count)
print(lily.count)

print(mike.age)
print(lily.age)
```
The output is
```
2    # the count shared by all people
2    # the count shared by all people
22   # the age unique to mike
25   # the age unique to lily
```
#### 3 ways of inheritance

```python
class Base(object):
    def __init__(self):
        print('base class')

class A(Base):
    def __init__(self):
        Base.__init__(self)

class B(Base):
    def __init__(self):
        super(B, self).__init__()

class C(Base):
    def __init__(self):
        super().__init__()
``` 

**Any differences?**

1. In class A, naming the parent class explicitly takes advtange in multiple inheritance cases.
2. super().__init__() is new in Python3, you can invoke super() without arguments.

