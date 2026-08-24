---
title: Idioms & Gotchas
subtopic: python-core
group: Terminology & Style
order: 3
---

#### EAFP vs LBYL

```python
# EAFP — "Easier to Ask Forgiveness than Permission" (preferred)
try:
    value = d['key']
except KeyError:
    value = default

# LBYL — "Look Before You Leap"
value = d['key'] if 'key' in d else default
```

#### Mutable default argument

```python
def bad(item, bucket=[]):     # ⚠ list shared across all calls!
    bucket.append(item)
    return bucket

def good(item, bucket=None):
    if bucket is None:
        bucket = []
    bucket.append(item)
    return bucket
```
