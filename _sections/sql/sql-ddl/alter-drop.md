---
title: ALTER & DROP
subtopic: sql-ddl
group: Altering & Managing Schema
order: 1
---

#### Schema changes

```sql
ALTER TABLE users ADD COLUMN phone VARCHAR(20);
ALTER TABLE users DROP COLUMN phone;
ALTER TABLE users ALTER COLUMN age SET NOT NULL;      -- PostgreSQL
ALTER TABLE users RENAME COLUMN email TO email_address;
DROP TABLE IF EXISTS temp_users;
```
