---
title: File I/O
subtopic: python-core
group: Files & System
order: 1
---

#### Read & write

```python
with open('file.txt', encoding='utf-8') as f:
    content = f.read()          # whole file as str
    # f.readline()   f.readlines()
    for line in f:              # memory-efficient streaming
        process(line)

with open('out.txt', 'w', encoding='utf-8') as f:
    f.write('text\n')
    f.writelines(lines)
```

#### Modes & structured files

```python
'r'  read (default)     'w'  write (truncate)
'a'  append             'x'  create, fail if exists
'b'  binary (rb, wb)    '+'  read+write (r+)

import json, csv
data = json.load(open('d.json'))
rows = csv.DictReader(open('d.csv'))
```
