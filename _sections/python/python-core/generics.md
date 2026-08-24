---
title: Generics & TypeVar
subtopic: python-core
group: Type Hints
order: 2
---

#### 3.12+ syntax

```python
def first[T](items: list[T]) -> T:
    return items[0]

class Box[T]:
    def __init__(self, value: T):
        self.value = value

type Vector = list[float]        # type alias
```

#### Classic TypeVar syntax

```python
from typing import TypeVar, Generic

T = TypeVar('T')
N = TypeVar('N', int, float)     # constrained

def first(items: list[T]) -> T: ...

class Box(Generic[T]):
    def __init__(self, value: T):
        self.value = value
```
