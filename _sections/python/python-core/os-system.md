---
title: os / sys / subprocess
subtopic: python-core
group: Files & System
order: 3
---

#### os & sys

```python
import os, sys
os.environ.get('PATH')       os.environ['KEY'] = 'v'
os.getcwd()   os.chdir(p)    os.listdir('.')
os.makedirs(p, exist_ok=True)   os.remove(f)
sys.argv                     # command-line args
sys.exit(1)      sys.platform      sys.version
```

#### subprocess & shutil

```python
import subprocess
r = subprocess.run(['ls', '-l'], capture_output=True,
                   text=True, check=True)
r.stdout   r.returncode

import shutil
shutil.copy(src, dst)    shutil.move(src, dst)
shutil.rmtree(dir)       shutil.which('git')
```
