---
title: Iterator Protocol
subtopic: python-core
group: Comprehensions & Generators
order: 3
---

#### __iter__ / __next__

```python
class Countdown:
    def __init__(self, n):
        self.n = n
    def __iter__(self):
        return self              # the iterator is itself
    def __next__(self):
        if self.n <= 0:
            raise StopIteration  # signals the end
        self.n -= 1
        return self.n + 1

for x in Countdown(3):          # 3, 2, 1
    print(x)
```

#### Manual iteration

```python
it = iter([1, 2, 3])   # get an iterator from an iterable
next(it)               # 1
next(it, 'done')       # default instead of StopIteration
```
