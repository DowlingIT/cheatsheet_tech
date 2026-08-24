---
title: Functions
subtopic: python-core
group: Functions
order: 1
---

#### Signatures & defaults

```python
def greet(name: str, greeting: str = 'Hello') -> str:
    return f'{greeting}, {name}!'

def func(*args, **kwargs):
    # args → tuple, kwargs → dict
    pass

def strict(a, b, *, name: str):   # keyword-only after *
    pass

def pos(a, b, /, c):              # positional-only before /
    pass

strict(1, 2, name='Alice')
```

#### Lambdas & higher-order

```python
double = lambda x: x * 2

from functools import reduce
list(map(lambda x: x**2, [1, 2, 3]))    # [1, 4, 9]
list(filter(lambda x: x > 0, items))
reduce(lambda acc, x: acc + x, items, 0)

sorted(people, key=lambda p: (p.age, p.name))
```
