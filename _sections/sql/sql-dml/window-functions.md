---
title: Window Basics
subtopic: sql-dml
group: Window Functions
order: 1
---

#### OVER / PARTITION BY

A window function computes across related rows **without collapsing them** (unlike `GROUP BY`).

```sql
SELECT name, department, salary,
  SUM(salary) OVER ()                         AS company_total,
  SUM(salary) OVER (PARTITION BY department)  AS dept_total,
  salary * 100.0
    / SUM(salary) OVER (PARTITION BY department) AS pct_of_dept
FROM employees;
```

- `OVER ()` — whole result set is one window
- `PARTITION BY` — restarts the calculation per group (like `GROUP BY`, but keeps every row)
- `ORDER BY` inside `OVER` — orders rows within each partition (needed for ranking, `LAG`, running totals)
- Evaluated **after** `WHERE`/`GROUP BY`/`HAVING` — can't filter on them there; wrap in a CTE/subquery
