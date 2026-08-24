---
title: Types & Casting
subtopic: python-core
group: Variables & Types
order: 2
---

#### Built-in types

```python
int   float   complex   bool   str   bytes
list  tuple   dict      set    frozenset   NoneType

type(x)                      # returns type object
isinstance(x, int)           # True / False
isinstance(x, (int, float))  # accepts multiple types
```

#### Casting

```python
int('42')        int(3.9)     # 3  (truncates)
float('3.14')    str(42)
bool(0)          # False — also: '', [], {}, None
list('abc')      # ['a', 'b', 'c']
tuple([1, 2])    # (1, 2)
set([1, 1, 2])   # {1, 2}
bytes('hello', 'utf-8')
```

#### Constants & None

```python
None    True    False

MAX = 100      # convention: UPPER_CASE for constants
from typing import Final
MAX: Final = 100
```
