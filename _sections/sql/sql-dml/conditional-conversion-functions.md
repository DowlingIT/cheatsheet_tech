---
title: Conditional & Conversion Functions
subtopic: sql-dml
group: Built-in Functions
order: 4
---

#### Common functions

```sql
COALESCE(nickname, first_name, 'Unknown')   -- first non-null value, ANSI-standard
NULLIF(a, b)                                  -- NULL if a = b, else a
CASE WHEN age >= 18 THEN 'adult' ELSE 'minor' END
CAST(price AS DECIMAL(10,2))                    -- standard, portable conversion syntax
```
