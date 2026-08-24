---
title: Context Managers
subtopic: python-core
group: Classes & OOP
order: 4
---

#### with statement

```python
with open('f') as f, lock:       # multiple managers
    ...
# __enter__ runs on entry; __exit__ on exit, even on error

class Timer:
    def __enter__(self):
        self.start = time.time()
        return self
    def __exit__(self, exc_type, exc, tb):
        print(time.time() - self.start)
        # return True to suppress the exception
```

#### contextlib

```python
from contextlib import contextmanager, suppress

@contextmanager
def transaction(db):
    db.begin()
    try:
        yield db                 # code inside `with` runs here
        db.commit()
    except Exception:
        db.rollback()
        raise

with suppress(FileNotFoundError):
    os.remove('maybe.txt')
```
