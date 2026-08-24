---
title: Typing Basics
subtopic: python-core
group: Type Hints
order: 1
---

#### Common annotations

```python
x: int = 1
name: str | None = None            # optional (3.10+)
items: list[str] = []
pairs: dict[str, int] = {}
coords: tuple[float, float] = (0.0, 0.0)
row: tuple[int, ...] = (1, 2, 3)   # variable-length
```

#### typing module

```python
from typing import Optional, Union, Any, Callable
from collections.abc import Iterable, Sequence, Mapping

Optional[str]                # == str | None
Union[int, str]              # == int | str
Callable[[int, str], bool]   # (int, str) -> bool
def total(xs: Iterable[int]) -> int: ...
config: dict[str, Any]
```
