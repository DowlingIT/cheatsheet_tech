---
title: collections Module
subtopic: python-core
group: Collections
order: 4
---

#### deque — fast at both ends

```python
from collections import deque
dq = deque([1, 2, 3], maxlen=5)
dq.appendleft(0)      dq.append(4)
dq.popleft()          dq.pop()
dq.rotate(1)          # O(1) push/pop at either end
```

#### OrderedDict & ChainMap

```python
from collections import OrderedDict, ChainMap

od = OrderedDict()
od.move_to_end('k')    od.popitem(last=False)   # FIFO pop

defaults = {'color': 'red', 'size': 'M'}
cfg = ChainMap(overrides, defaults)   # layered lookup
cfg['color']           # first map that has the key wins
```
