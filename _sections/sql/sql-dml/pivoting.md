---
title: Pivoting Rows ↔ Columns
subtopic: sql-dml
group: Aggregation
order: 2
---

#### Pivot: conditional aggregation (works everywhere)

```sql
SELECT product,
  SUM(CASE WHEN quarter = 'Q1' THEN amount END) AS q1,
  SUM(CASE WHEN quarter = 'Q2' THEN amount END) AS q2,
  SUM(CASE WHEN quarter = 'Q3' THEN amount ELSE 0 END) AS q3,  -- ELSE 0 → 0, not NULL
  COUNT(CASE WHEN status = 'open' THEN 1 END)   AS open_count
FROM sales
GROUP BY product;

-- ANSI FILTER clause (PostgreSQL, SQLite 3.30+; not SQL Server / MySQL)
SUM(amount) FILTER (WHERE quarter = 'Q1') AS q1
```

#### Unpivot: UNION ALL

```sql
SELECT product, 'Q1' AS quarter, q1 AS amount FROM quarterly
UNION ALL
SELECT product, 'Q2', q2 FROM quarterly;
```

Output columns are fixed when the query is written. For column names taken from the data, you need dynamic SQL.
