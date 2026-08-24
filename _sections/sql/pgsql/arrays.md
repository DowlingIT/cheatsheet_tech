---
title: Arrays
subtopic: pgsql
group: Postgres-Specific Features
order: 1
---

#### Array operations

```sql
SELECT ARRAY[1, 2, 3];
SELECT * FROM users WHERE 'admin' = ANY(roles);      -- roles is a TEXT[] column
SELECT unnest(roles) FROM users;                        -- expand array to rows
SELECT array_agg(name) FROM users;                        -- rows → array, inverse of unnest
```
