---
title: Operators & Assignment
subtopic: python-core
group: Variables & Types
order: 3
---

#### Augmented assignment

```python
x += 1     x -= 1     x *= 2     x /= 2
x //= 2    x %= 3     x **= 2            # floor, mod, power
x &= y     x |= y     x ^= y    x <<= 1  # bitwise
lst += [4]         # extends in place
s += 'text'        # rebinds (str is immutable)
```

#### Comparison, identity, membership

```python
==  !=  <  >  <=  >=
a is b        a is not b        # identity (same object)
x in coll     x not in coll     # membership
0 < x < 10                      # chained comparison
```

#### Truthiness & line continuation

```python
bool('')  bool([])  bool(0)  bool(None)   # all False
total = 1 + 2 + \
        3 + 4                # explicit continuation
total = (1 + 2 +
         3 + 4)              # implicit inside () [] {}
```
