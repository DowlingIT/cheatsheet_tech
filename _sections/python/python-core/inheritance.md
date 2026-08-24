---
title: Inheritance & Dunder Methods
subtopic: python-core
group: Classes & OOP
order: 2
---

#### Inheritance

```python
class Dog(Animal):
    def __init__(self, name: str, breed: str):
        super().__init__(name)       # call parent __init__
        self.breed = breed

    def speak(self) -> str:
        return 'woof'

class ServiceDog(Dog, CertifiedMixin):  # multiple inheritance
    pass

issubclass(Dog, Animal)   isinstance(dog, Animal)
```

#### Common dunder methods

```python
__str__      # str(obj)            human-readable string
__repr__     # repr(obj)           debug / unambiguous
__len__      # len(obj)
__eq__       # obj == other
__lt__       # obj < other         (enables sorting)
__hash__     # hash(obj)           required for dict keys
__contains__ # x in obj
__iter__     # for x in obj
__enter__ / __exit__   # with statement
__call__     # obj()               callable instance
```
