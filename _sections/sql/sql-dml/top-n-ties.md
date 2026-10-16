---
title: Top-N per Group & WITH TIES
subtopic: sql-dml
group: Window Functions
order: 3
---

#### Top N per partition

```sql
WITH ranked AS (
  SELECT *, ROW_NUMBER() OVER (
    PARTITION BY department ORDER BY salary DESC, id) AS rn
  FROM employees
)
SELECT * FROM ranked WHERE rn <= 3;   -- use RANK() to keep ties at the cutoff
```

Same pattern with `rn = 1` dedupes (keep newest row per key), with `rn > 1` finds the duplicates to delete.

#### WITH TIES

Returns the first N rows **plus any rows tied with the Nth** on the `ORDER BY` values (requires `ORDER BY`).

```sql
SELECT * FROM employees ORDER BY salary DESC
FETCH FIRST 3 ROWS WITH TIES;         -- ANSI: PostgreSQL 13+, Oracle 12c+
SELECT TOP 3 WITH TIES * FROM employees
ORDER BY salary DESC;                 -- SQL Server
```

MySQL / SQLite have no `WITH TIES` — use the CTE above with `RANK()` and `<= 3`.
