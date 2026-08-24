---
title: Indexes
subtopic: sql-ddl
group: Indexes
order: 1
---

#### Creating indexes

```sql
CREATE INDEX idx_users_email ON users (email);
CREATE UNIQUE INDEX idx_users_email_unique ON users (email);
CREATE INDEX idx_orders_user_status ON orders (user_id, status);   -- composite

DROP INDEX idx_users_email;
```
