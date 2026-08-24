---
title: Class Structure
subtopic: python-core
group: Classes & OOP
order: 1
---

#### Anatomy

```python
class Animal:
    count = 0                       # class variable

    def __init__(self, name: str, age: int = 0):
        self.name = name            # instance variable
        self._age = age             # convention: protected
        Animal.count += 1

    @property
    def age(self) -> int:
        return self._age

    @age.setter
    def age(self, value: int):
        if value < 0:
            raise ValueError('age must be non-negative')
        self._age = value

    def __repr__(self) -> str:
        return f'Animal({self.name!r}, age={self._age})'
```
