---
title: Numeric & Boolean Types
subtopic: sql-ddl
group: Data Types
order: 1
---

#### Numeric types

```sql
INT / INTEGER   BIGINT   SMALLINT   TINYINT      -- whole numbers, varying range
DECIMAL(10,2) / NUMERIC(10,2)                       -- exact, fixed precision & scale
FLOAT   REAL   DOUBLE PRECISION                        -- approximate — never use for money
```

#### Boolean

```sql
BOOLEAN                    -- true/false (PostgreSQL); MySQL/SQLite: TINYINT(1) or 0/1
SELECT true, false;
WHERE active = TRUE
```
