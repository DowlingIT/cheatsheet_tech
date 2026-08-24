---
title: Subqueries
subtopic: sql-dml
group: Subqueries & CTEs
order: 1
---

#### Scalar & correlated

```sql
SELECT name FROM users
WHERE id = (SELECT user_id FROM orders ORDER BY total DESC LIMIT 1);

SELECT * FROM users u
WHERE EXISTS (SELECT 1 FROM orders o WHERE o.user_id = u.id);   -- correlated

SELECT * FROM products WHERE id NOT IN (SELECT product_id FROM order_items);
```
