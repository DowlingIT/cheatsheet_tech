---
title: Conditional & Conversion Functions
subtopic: mysql
group: Built-in Functions
order: 4
---

#### Common functions

```sql
IFNULL(nickname, 'Unknown')        -- 2 args only
COALESCE(a, b, c)                    -- any number of args
NULLIF(a, b)
IF(age >= 18, 'adult', 'minor')        -- inline conditional (not IIF)
CASE WHEN age >= 18 THEN 'adult' ELSE 'minor' END
CAST(price AS DECIMAL(10,2))
CONVERT(price, DECIMAL(10,2))
```
