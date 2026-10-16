---
title: PIVOT & UNPIVOT
subtopic: tsql
group: Querying
order: 2
---

#### PIVOT

```sql
SELECT product, [Q1], [Q2], [Q3], [Q4]
FROM (SELECT product, quarter, amount FROM sales) AS src
PIVOT (SUM(amount) FOR quarter IN ([Q1], [Q2], [Q3], [Q4])) AS p;
```

- Every source column not named in `PIVOT` becomes an implicit `GROUP BY`. Select only the needed columns in a derived table/CTE first
- One aggregate only. For several, use `SUM(CASE …)` instead

#### UNPIVOT

```sql
SELECT product, quarter, amount
FROM quarterly
UNPIVOT (amount FOR quarter IN ([Q1], [Q2], [Q3], [Q4])) AS u;
```

`UNPIVOT` drops NULLs. To keep them, use `CROSS APPLY (VALUES ('Q1', Q1), ('Q2', Q2)) v(quarter, amount)`.
