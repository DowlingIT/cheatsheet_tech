---
title: String Functions
subtopic: tsql
group: Built-in Functions
order: 1
---

#### Common functions

```sql
LEN(name)                        -- T-SQL uses LEN, not LENGTH
SUBSTRING(name, 1, 3)
CHARINDEX('foo', name)             -- position of a substring
LEFT(name, 3)   RIGHT(name, 3)
UPPER(name)   LOWER(name)   TRIM(name)
REPLACE(name, 'a', 'b')
CONCAT(first, ' ', last)             -- or the + operator
STRING_AGG(name, ', ')                 -- concatenate rows into one string
```
