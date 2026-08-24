---
title: Comprehensions
subtopic: python-core
group: Comprehensions & Generators
order: 1
---

#### List / dict / set

```python
squares = [x**2 for x in range(10)]
evens   = [x for x in range(20) if x % 2 == 0]
pairs   = [(x, y) for x in [1, 2] for y in ['a', 'b']]

inv     = {v: k for k, v in original.items()}   # dict
unique_lens = {len(w) for w in words}            # set

flat = [x for row in matrix for x in row]        # flatten
```

#### Conditional & walrus

```python
labels = ['even' if x % 2 == 0 else 'odd' for x in range(5)]

# Walrus operator — avoid recomputing in condition
results = [y for x in data if (y := transform(x)) is not None]
```
