---
title: Lists
subtopic: python-core
group: Collections
order: 1
---

#### Common operations

```python
lst = [1, 2, 3]
lst.append(4)          lst.extend([5, 6])
lst.insert(0, 0)       lst.pop()         lst.pop(1)
lst.remove(3)          # removes first occurrence
lst.sort()             lst.sort(key=lambda x: -x)
lst.reverse()          lst.index(2)      lst.count(2)
len(lst)               sum(lst)
```

#### Slicing

```python
lst[1:3]     # [2, 3]
lst[::-1]    # reversed
lst[::2]     # every other element
lst[:3]      # first 3
lst[-2:]     # last 2

merged = [*lst1, *lst2]      # spread merge
copy   = lst.copy()          # shallow copy
```
