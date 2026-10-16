---
title: "Pivot: FILTER & crosstab"
subtopic: pgsql
group: Postgres-Specific Features
order: 4
---

#### FILTER (preferred)

```sql
SELECT product,
  SUM(amount) FILTER (WHERE quarter = 'Q1') AS q1,
  SUM(amount) FILTER (WHERE quarter = 'Q2') AS q2,
  COUNT(*)    FILTER (WHERE status = 'open') AS open_count
FROM sales GROUP BY product;
```

#### crosstab (tablefunc extension)

```sql
CREATE EXTENSION IF NOT EXISTS tablefunc;
SELECT * FROM crosstab(
  $$SELECT product, quarter, SUM(amount) FROM sales GROUP BY 1, 2 ORDER BY 1, 2$$,
  $$VALUES ('Q1'), ('Q2'), ('Q3'), ('Q4')$$   -- category list keeps gaps aligned
) AS ct(product text, q1 numeric, q2 numeric, q3 numeric, q4 numeric);
```

#### Unpivot with LATERAL VALUES

```sql
SELECT q.product, v.quarter, v.amount
FROM quarterly q
CROSS JOIN LATERAL (VALUES ('Q1', q.q1), ('Q2', q.q2)) AS v(quarter, amount);
```
