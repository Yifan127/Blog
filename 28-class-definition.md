### Class and Object

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

#### Attribute references and instantiation.
* Attribute references
    1. Person.count
    2. Person.displayPerson
* Instantiation

    mike = Person('Mike', 22)

