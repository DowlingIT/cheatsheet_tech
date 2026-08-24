---
title: Variables & Assignment
subtopic: python-core
group: Variables & Types
order: 1
---

#### Assignment

```python
name = 'Alice'
x = y = z = 0              # chained assignment
a, b, c = 1, 2, 3          # tuple unpacking
first, *rest = [1, 2, 3, 4]  # starred unpacking
_, second, *_ = items       # discard with _
a, b = b, a                 # swap
```

#### Type annotations

```python
name: str = 'Alice'
count: int = 0
items: list[str] = []
mapping: dict[str, int] = {}
value: str | None = None    # union (3.10+)

def greet(name: str, age: int = 0) -> str:
    return f'Hello {name}'
```
