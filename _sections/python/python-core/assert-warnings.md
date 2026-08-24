---
title: assert, warnings & Groups
subtopic: python-core
group: Exceptions
order: 3
---

#### assert

```python
assert x > 0, 'x must be positive'   # raises AssertionError
# stripped when run with python -O
# use for invariants/tests, never for input validation
```

#### warnings

```python
import warnings
warnings.warn('deprecated', DeprecationWarning)
warnings.filterwarnings('ignore', category=DeprecationWarning)
```

#### ExceptionGroup (3.11+)

```python
try:
    ...
except* ValueError as eg:      # handle a subgroup
    ...
raise ExceptionGroup('multi', [ValueError(), TypeError()])
```
