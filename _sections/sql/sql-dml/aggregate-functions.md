---
title: Aggregate Functions
subtopic: sql-dml
group: Aggregation
order: 1
---

#### Grouping & aggregating

```sql
SELECT COUNT(*), AVG(price), SUM(qty), MIN(price), MAX(price)
FROM orders;

SELECT customer_id, COUNT(*) AS order_count
FROM orders
GROUP BY customer_id
HAVING COUNT(*) > 5;      -- filters after grouping (WHERE filters before)
```
