---
title: Encoding & JSON
subtopic: python-core
group: Strings, Dates & Encoding
order: 4
---

#### Bytes ↔ str

```python
b = 'héllo'.encode('utf-8')          # str → bytes
b.decode('utf-8')                     # bytes → str
'x'.encode('ascii', errors='replace') # or 'ignore'
ord('A')   chr(65)                    # code point ↔ char

import base64
base64.b64encode(b)   base64.b64decode(s)
```

#### JSON

```python
import json
json.dumps({'a': 1}, indent=2)   # obj → str
json.loads('{"a": 1}')           # str → obj
json.dump(obj, file)             # write to file
json.load(file)                  # read from file
# json.dumps(obj, default=str)   for datetime / Decimal
```
