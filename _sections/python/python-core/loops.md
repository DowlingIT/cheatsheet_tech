---
title: Loops
subtopic: python-core
group: Control Flow
order: 2
---

#### for / while

```python
for item in iterable:
    if item == skip: continue
    if item == stop: break
else:
    pass  # runs if loop completed without break

while condition:
    do_something()
```

#### Iteration helpers

```python
enumerate(['a', 'b', 'c'])           # (0,'a') (1,'b') (2,'c')
zip([1, 2], ['a', 'b'])              # (1,'a') (2,'b')
zip([1, 2], ['a', 'b'], strict=True) # raises if lengths differ
reversed([1, 2, 3])

range(10)         range(2, 10)       range(0, 10, 2)

sorted(items, key=lambda x: x.name, reverse=True)
min(items, key=lambda x: x.age)
max(items, key=lambda x: x.age)
```
