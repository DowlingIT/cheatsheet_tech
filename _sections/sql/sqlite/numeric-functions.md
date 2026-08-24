---
title: Numeric Functions
subtopic: sqlite
group: Built-in Functions
order: 2
---

#### Common functions

```sql
round(price, 2)
abs(-5)
max(a, b)   min(a, b)      -- 2+ args = scalar comparison; 1 arg = aggregate
```

No built-in `power()`/`sqrt()` — either compute manually (`price * price`) or load the [math functions extension](https://sqlite.org/lang_mathfunc.html), included by default in most builds since 3.35.
