---
title: String Functions
subtopic: sqlite
group: Built-in Functions
order: 1
---

#### Common functions

```sql
name || ' ' || suffix        -- concatenation operator
length(name)
substr(name, 1, 3)
upper(name)   lower(name)   trim(name)
replace(name, 'a', 'b')
printf('%05d', 42)               -- sprintf-style formatting
group_concat(name, ', ')            -- aggregate concat
```
