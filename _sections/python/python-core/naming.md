---
title: Naming Conventions (PEP 8)
subtopic: python-core
group: Terminology & Style
order: 2
---

#### Conventions

```python
snake_case     # functions, variables, methods, modules
PascalCase     # classes, exceptions, type variables
UPPER_SNAKE    # module-level constants
_leading       # internal / "protected" (convention only)
__leading      # name-mangled to _Class__name
__dunder__     # reserved for Python's special methods
trailing_      # avoid keyword clash: class_, type_, id_
```

#### Name mangling

```python
class Base:
    def __init__(self):
        self.__secret = 1        # stored as _Base__secret

b = Base()
b._Base__secret                  # 1 — not truly private
```
