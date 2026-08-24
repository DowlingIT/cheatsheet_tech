---
title: Generators & itertools
subtopic: python-core
group: Comprehensions & Generators
order: 2
---

#### Generator functions

```python
def fibonacci():
    a, b = 0, 1
    while True:
        yield a
        a, b = b, a + b

gen = fibonacci()
next(gen)    # 0
next(gen)    # 1

def read_chunks(file, size=4096):
    while chunk := file.read(size):
        yield chunk
```

#### Generator expressions & itertools

```python
gen_exp = (x**2 for x in range(1_000_000))   # lazy — not a list
sum(x**2 for x in range(1000))

import itertools
itertools.islice(gen, 5)              # take first 5
itertools.chain(iter1, iter2)         # concatenate
itertools.groupby(items, key=attrgetter('category'))
itertools.product([1, 2], ['a', 'b']) # cartesian product
itertools.combinations(items, 2)
itertools.accumulate([1, 2, 3, 4])    # running totals
```
