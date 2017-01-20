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
#### Attribute references and instantiation.
* Attribute references
1. Person.count
2. Person.__init__