---
title: Dicts
subtopic: python-core
group: Collections
order: 2
---

#### Operations

```python
d = {'a': 1, 'b': 2}
d['c'] = 3
d.get('x', 0)                 # default if missing
d.setdefault('x', []).append(1)
d.pop('a', None)               # remove & return
del d['b']

d.keys()   d.values()   d.items()   # views
'a' in d                            # membership test
{**d1, **d2}                        # merge (3.9+: d1 | d2)
d.update({'c': 3, 'd': 4})
```

#### Patterns

```python
from collections import defaultdict, Counter

word_count = Counter(['a', 'b', 'a'])
word_count.most_common(3)          # [('a', 2), ('b', 1)]
word_count['missing']              # 0 — no KeyError

groups = defaultdict(list)
for item in items:
    groups[item.category].append(item)
```
