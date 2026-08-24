---
title: Join Types
subtopic: sql-dml
group: Joins
order: 1
---

#### Joining tables

```sql
SELECT o.id, u.name
FROM orders o
INNER JOIN users u ON o.user_id = u.id;      -- only matching rows

SELECT u.name, o.id
FROM users u
LEFT JOIN orders o ON o.user_id = u.id;      -- all users, matched orders or NULL

-- also: RIGHT JOIN, FULL OUTER JOIN, CROSS JOIN (Cartesian product)
SELECT a.name, b.name FROM employees a
JOIN employees b ON a.manager_id = b.id;     -- self join
```
