---
title: Offsets & Running Totals
subtopic: sql-dml
group: Window Functions
order: 4
---

#### LAG / LEAD / FIRST_VALUE

```sql
SELECT order_date, amount,
  LAG(amount)       OVER (ORDER BY order_date)     AS prev_amount,
  LEAD(amount, 1, 0) OVER (ORDER BY order_date)    AS next_amount, -- offset, default
  amount - LAG(amount) OVER (ORDER BY order_date)  AS change,
  FIRST_VALUE(amount) OVER (ORDER BY order_date)   AS first_amount
FROM orders;
```

#### Frames: running totals & moving averages

```sql
SUM(amount) OVER (ORDER BY order_date
  ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW)   AS running_total,
AVG(amount) OVER (ORDER BY order_date
  ROWS BETWEEN 6 PRECEDING AND CURRENT ROW)           AS moving_avg_7
```

- Default frame with `ORDER BY` is `RANGE ... CURRENT ROW` — tied dates are summed together; use `ROWS` for row-by-row
- `LAST_VALUE` gotcha: default frame ends at current row — add `ROWS BETWEEN UNBOUNDED PRECEDING AND UNBOUNDED FOLLOWING`
