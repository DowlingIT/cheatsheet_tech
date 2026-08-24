---
title: Filtering & Operators
subtopic: sql-dml
group: Querying
order: 2
---

#### WHERE clause

```sql
SELECT * FROM users WHERE age > 18;
SELECT * FROM users WHERE status IN ('active', 'pending');
SELECT * FROM users WHERE name LIKE 'A%';       -- prefix match
SELECT * FROM users WHERE age BETWEEN 18 AND 65;
SELECT * FROM users WHERE deleted_at IS NULL;
SELECT * FROM users WHERE active = true AND age > 18;
```
