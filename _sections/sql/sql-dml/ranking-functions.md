---
title: Ranking Functions
subtopic: sql-dml
group: Window Functions
order: 2
---

#### ROW_NUMBER vs RANK vs DENSE_RANK

```sql
SELECT name, salary,
  ROW_NUMBER() OVER (ORDER BY salary DESC) AS row_num,
  RANK()       OVER (ORDER BY salary DESC) AS rnk,
  DENSE_RANK() OVER (ORDER BY salary DESC) AS dense_rnk,
  NTILE(2)     OVER (ORDER BY salary DESC) AS half
FROM employees;
```

| salary | ROW_NUMBER | RANK | DENSE_RANK | NTILE(2) |
|--------|-----------:|-----:|-----------:|---------:|
| 100    | 1 | 1 | 1 | 1 |
| 90     | 2 | 2 | 2 | 1 |
| 90     | 3 | 2 | 2 | 2 |
| 80     | 4 | **4** | **3** | 2 |

- `ROW_NUMBER` — always unique; ties broken arbitrarily (add a tiebreaker: `ORDER BY salary DESC, id`)
- `RANK` — ties share a rank, then **skips** (1, 2, 2, 4)
- `DENSE_RANK` — ties share a rank, **no gaps** (1, 2, 2, 3)
- `NTILE(n)` — splits rows into `n` roughly equal buckets
