---
title: Conditional & Conversion Functions
subtopic: pgsql
group: Built-in Functions
order: 4
---

#### Common functions

```sql
COALESCE(nickname, first_name, 'Unknown')
NULLIF(a, b)
CASE WHEN age >= 18 THEN 'adult' ELSE 'minor' END
CAST(price AS DECIMAL(10,2))
price::DECIMAL(10,2)          -- Postgres shorthand cast
```
