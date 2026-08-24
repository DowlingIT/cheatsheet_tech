---
title: String Methods
subtopic: python-core
group: Strings, Dates & Encoding
order: 1
---

#### Transform & test

```python
s.upper()   s.lower()   s.title()   s.capitalize()
s.strip()   s.lstrip()  s.rstrip()  s.strip('/')
s.replace('a', 'b')     s.zfill(5)  s.center(10)
s.startswith('http')    s.endswith('.py')
s.isdigit()  s.isalpha()  s.isspace()
```

#### Split, join, search

```python
'a,b,c'.split(',')          # ['a', 'b', 'c']
'  a b  '.split()           # ['a', 'b'] — any whitespace
'l1\nl2'.splitlines()       # ['l1', 'l2']
','.join(['a', 'b', 'c'])   # 'a,b,c'
s.find('x')      # index, or -1 if absent
s.index('x')     # index, or ValueError
s.count('x')     'sub' in s
```
