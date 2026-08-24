---
title: CTEs
subtopic: sql-dml
group: Subqueries & CTEs
order: 2
---

#### WITH & recursive

```sql
WITH recent_orders AS (
  SELECT * FROM orders WHERE created_at > NOW() - INTERVAL '30 days'
)
SELECT customer_id, COUNT(*) FROM recent_orders GROUP BY customer_id;

WITH RECURSIVE org_chart AS (
  SELECT id, name, manager_id FROM employees WHERE manager_id IS NULL
  UNION ALL
  SELECT e.id, e.name, e.manager_id
  FROM employees e JOIN org_chart o ON e.manager_id = o.id
)
SELECT * FROM org_chart;
```
