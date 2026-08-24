---
title: Decorators
subtopic: python-core
group: Functions
order: 2
---

#### Function decorators

```python
from functools import wraps

def log_call(func):
    @wraps(func)          # preserves __name__, __doc__
    def wrapper(*args, **kwargs):
        print(f'calling {func.__name__}')
        return func(*args, **kwargs)
    return wrapper

@log_call
def my_func(): ...
```

#### Built-in descriptors

```python
class MyClass:
    @staticmethod
    def utility(): ...        # no self or cls

    @classmethod
    def create(cls): ...      # receives the class

    @property
    def name(self): return self._name

    @name.setter
    def name(self, v): self._name = v

    @name.deleter
    def name(self): del self._name
```
