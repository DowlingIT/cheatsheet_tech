---
title: Exceptions
subtopic: python-core
group: Exceptions
order: 1
---

#### try / except / finally

```python
try:
    result = 10 / divisor
except ZeroDivisionError as e:
    print(f'Error: {e}')
except (TypeError, ValueError):
    raise                        # re-raise current exception
else:
    print('success')             # runs only if no exception
finally:
    cleanup()                    # always runs

raise ValueError('must be positive')
raise RuntimeError('failed') from original_exc   # chaining
```

#### Custom exceptions

```python
class AppError(Exception):
    pass

class NotFoundError(AppError):
    def __init__(self, resource: str, id: int):
        super().__init__(f'{resource} #{id} not found')
        self.resource = resource
        self.id = id

raise NotFoundError('Post', 42)
```
