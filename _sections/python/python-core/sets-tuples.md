---
title: Sets & Tuples
subtopic: python-core
group: Collections
order: 3
---

#### Sets

```python
s = {1, 2, 3}
s.add(4)          s.discard(5)    # discard: no error if absent
s.remove(3)                        # KeyError if absent

s | {4, 5}        # union
s & {2, 3}        # intersection
s - {2}           # difference
s ^ {2, 4}        # symmetric difference
{2} <= s          # subset
```

#### Tuples & NamedTuples

```python
point = (1, 2)
x, y = point                  # unpack
single = (42,)                 # trailing comma required

from collections import namedtuple
from typing import NamedTuple

Point = namedtuple('Point', ['x', 'y'])

class Point(NamedTuple):       # preferred: typed
    x: float
    y: float

p = Point(1.0, 2.0)
p.x   p._asdict()   p._replace(x=5.0)
```
