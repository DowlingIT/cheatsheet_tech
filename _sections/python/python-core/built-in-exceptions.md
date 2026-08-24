---
title: Built-in Exceptions
subtopic: python-core
group: Exceptions
order: 2
---

#### Common built-ins

```
Exception            base for all catchable errors
├ ValueError         right type, wrong value
├ TypeError          wrong type
├ KeyError           missing dict key
├ IndexError         list index out of range
├ AttributeError     missing attribute
├ FileNotFoundError  (subclass of OSError)
├ StopIteration      iterator exhausted
└ RuntimeError       generic runtime failure
```

#### Inspecting an exception

```python
try:
    ...
except Exception as e:
    type(e).__name__     # 'ValueError'
    str(e)   e.args      # message / arg tuple
    import traceback
    traceback.format_exc()   # full traceback string
```
