---
title: pathlib
subtopic: python-core
group: Files & System
order: 2
---

#### Paths

```python
from pathlib import Path

p = Path('/home/user') / 'docs' / 'file.txt'   # / joins
p.name        # 'file.txt'     p.stem    # 'file'
p.suffix      # '.txt'         p.parent  # the dir
p.exists()    p.is_file()   p.is_dir()
p.resolve()   Path.cwd()    Path.home()
```

#### Read, write, iterate

```python
p.read_text(encoding='utf-8')   p.write_text('hi')
p.read_bytes()                  p.write_bytes(b)
p.mkdir(parents=True, exist_ok=True)
p.unlink(missing_ok=True)       # delete file
list(p.glob('*.py'))            p.rglob('*.py')  # recursive
```
