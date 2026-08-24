---
title: DISTINCT ON & LATERAL
subtopic: pgsql
group: Postgres-Specific Features
order: 3
---

#### DISTINCT ON

```sql
SELECT DISTINCT ON (customer_id) *          -- one row per customer_id
FROM orders
ORDER BY customer_id, created_at DESC;        -- most recent order per customer
```

#### LATERAL joins

```sql
SELECT u.name, recent.*
FROM users u,
LATERAL (
  SELECT * FROM orders o WHERE o.user_id = u.id ORDER BY created_at DESC LIMIT 3
) recent;                                     -- top 3 orders per user, in one query
```
