---
title: Type Conversion & NULL Handling
subtopic: sql-ddl
group: Data Types
order: 5
---

#### Casting

```sql
CAST(price AS DECIMAL(10,2))
price::DECIMAL(10,2)              -- PostgreSQL shorthand
CONVERT(DECIMAL(10,2), price)       -- SQL Server
```

#### NULL semantics

```sql
COALESCE(nickname, first_name, 'Unknown')   -- first non-null value
NULLIF(a, b)                                  -- NULL if a = b, else a
a = NULL             -- always NULL/unknown — never compare to NULL with =
a IS NULL   a IS NOT NULL
a IS DISTINCT FROM b   -- NULL-safe equality (PostgreSQL)
```
