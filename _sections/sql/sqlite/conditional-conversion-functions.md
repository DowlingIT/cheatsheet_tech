---
title: Conditional & Conversion Functions
subtopic: sqlite
group: Built-in Functions
order: 4
---

#### Common functions

```sql
ifnull(nickname, 'Unknown')       -- 2 args only
coalesce(a, b, c)                   -- any number of args
nullif(a, b)
CASE WHEN age >= 18 THEN 'adult' ELSE 'minor' END
CAST(price AS DECIMAL(10,2))          -- follows type affinity rules, not strict types
```
