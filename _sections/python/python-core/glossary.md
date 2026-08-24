---
title: Glossary
subtopic: python-core
group: Terminology & Style
order: 1
---

#### Language terms

```
Expression   evaluates to a value  → x + 1, f(x), [i for i in xs]
Statement    performs an action    → if, for, x = 1, return
Dunder       __x__ "magic" method  → hooks syntax / operators
```

#### Object model terms

```
Iterable    has __iter__    loopable: list, str, dict, generator
Iterator    has __next__    yields one at a time, then exhausts
Mutable     changes in place  list, dict, set
Immutable   never changes     int, str, tuple, frozenset, bytes
Parameter   name in a def   (argument = the value passed at call)
```
