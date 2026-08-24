---
title: Conditional & Conversion Functions
subtopic: tsql
group: Built-in Functions
order: 4
---

#### Common functions

```sql
ISNULL(nickname, 'Unknown')         -- 2 args only, type comes from the first arg
COALESCE(a, b, c)                     -- ANSI-standard, any number of args
NULLIF(a, b)
IIF(age >= 18, 'adult', 'minor')        -- inline conditional
CAST(price AS DECIMAL(10,2))
CONVERT(VARCHAR, order_date, 120)         -- CONVERT takes a style code for formatting
TRY_CAST(val AS INT)   TRY_CONVERT(INT, val)  -- return NULL instead of erroring
```
