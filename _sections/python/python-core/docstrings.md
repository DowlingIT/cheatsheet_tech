---
title: Docstrings & help()
subtopic: python-core
group: Terminology & Style
order: 4
---

#### Triple-quoted docstrings

```python
def divide(a: float, b: float) -> float:
    """Return a divided by b.

    Args:
        a: numerator
        b: denominator (must be non-zero)
    Raises:
        ZeroDivisionError: if b == 0
    """
    return a / b

class Account:
    """A bank account."""     # first statement in module/class/func
```

#### Accessing docs

```python
divide.__doc__          # the raw docstring
help(divide)            # formatted help (REPL)
help(str)               # docs for any object or module
```
