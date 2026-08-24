---
title: Dataclasses
subtopic: python-core
group: Classes & OOP
order: 3
---

#### @dataclass

```python
from dataclasses import dataclass, field

@dataclass
class Point:
    x: float
    y: float = 0.0                        # default
    tags: list[str] = field(default_factory=list)  # mutable default

p = Point(1.0, 2.0)
p == Point(1.0, 2.0)         # auto __init__, __eq__, __repr__
```

#### Options & helpers

```python
@dataclass(frozen=True)      # immutable + hashable
@dataclass(order=True)       # adds <, >, <=, >=
@dataclass(slots=True)       # __slots__ (3.10+)

field(default=0, repr=False, compare=False)
from dataclasses import asdict, astuple
asdict(p)      astuple(p)
```
