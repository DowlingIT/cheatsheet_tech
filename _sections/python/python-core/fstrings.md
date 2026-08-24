---
title: f-strings & Format Spec
subtopic: python-core
group: Strings, Dates & Encoding
order: 2
---

#### f-strings

```python
name, n = 'Alice', 42
f'{name} has {n} items'
f'{n * 2}'                  # expressions allowed
f'{name=}'                  # name='Alice'  (debug, 3.8+)
f'{value!r}'                # !r repr   !s str   !a ascii
```

#### Format spec — `{value:spec}`

```python
f'{3.14159:.2f}'      # '3.14'       fixed precision
f'{1000000:,}'        # '1,000,000'  thousands sep
f'{0.25:.1%}'         # '25.0%'      percent
f'{42:05d}'           # '00042'      zero-pad to width
f"{'hi':>10}"         # right-align   < left   ^ center
f'{255:#x}'           # '0xff'       #b binary  #o octal
```
