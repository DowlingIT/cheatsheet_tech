---
title: TOP & WITH TIES
subtopic: tsql
group: Querying
order: 1
---

#### TOP variants

```sql
SELECT TOP (10) * FROM users ORDER BY created_at DESC;
SELECT TOP (@n) * FROM users ORDER BY created_at DESC;    -- variable needs parens
SELECT TOP (5) PERCENT * FROM orders ORDER BY total DESC;
SELECT TOP (3) WITH TIES * FROM employees
ORDER BY salary DESC;              -- may return >3 rows if salaries tie at #3
```

- `WITH TIES` requires `ORDER BY`; ties are judged on the `ORDER BY` columns only
- `OFFSET … FETCH` does **not** support `WITH TIES` in SQL Server — only `TOP` does
- `TOP` without `ORDER BY` returns arbitrary rows

#### Top 1 per group trick

```sql
SELECT TOP (1) WITH TIES *
FROM employees
ORDER BY ROW_NUMBER() OVER (PARTITION BY department ORDER BY salary DESC);
```

Every partition's row #1 ties at 1. Concise, but a CTE with `WHERE rn = 1` usually performs better.
