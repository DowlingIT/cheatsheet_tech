---
title: Protocols & Special Forms
subtopic: python-core
group: Type Hints
order: 3
---

#### Structural typing

```python
from typing import Protocol, runtime_checkable

@runtime_checkable
class Comparable(Protocol):
    def __lt__(self, other) -> bool: ...

def smallest(xs: list[Comparable]): ...
# any object with __lt__ qualifies — no inheritance needed
```

#### TypedDict / Literal / Final / cast

```python
from typing import TypedDict, Literal, Final, cast

class Movie(TypedDict):
    title: str
    year: int

mode: Literal['r', 'w', 'a'] = 'r'
MAX: Final = 100
obj = cast(User, raw)            # assert type to the checker
```
