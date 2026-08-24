---
title: String Functions
subtopic: pgsql
group: Built-in Functions
order: 1
---

#### Common functions

```sql
name || ' ' || suffix        -- concatenation operator
LENGTH(name)
SUBSTRING(name FROM 1 FOR 3)
UPPER(name)   LOWER(name)   TRIM(name)
REPLACE(name, 'a', 'b')
STRING_AGG(name, ', ')            -- aggregate concat, one row per group → one string
```
