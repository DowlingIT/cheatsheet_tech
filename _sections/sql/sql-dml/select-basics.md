---
title: SELECT Basics
subtopic: sql-dml
group: Querying
order: 1
---

#### Basic query

```sql
SELECT id, name, email FROM users;
SELECT * FROM users;                       -- avoid in production code
SELECT DISTINCT status FROM orders;
SELECT * FROM users ORDER BY created_at DESC;
SELECT * FROM users LIMIT 10 OFFSET 20;    -- pagination
SELECT name AS full_name FROM users;         -- alias
```
