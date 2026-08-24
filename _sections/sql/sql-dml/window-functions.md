---
title: Window Functions
subtopic: sql-dml
group: Aggregation
order: 2
---

#### OVER / PARTITION BY

```sql
SELECT
  name,
  salary,
  ROW_NUMBER() OVER (PARTITION BY department ORDER BY salary DESC) AS rank,
  RANK()       OVER (ORDER BY salary DESC) AS overall_rank,
  LAG(salary)  OVER (ORDER BY hired_at) AS prev_salary
FROM employees;
```
