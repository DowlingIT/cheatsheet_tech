---
title: Views
subtopic: sql-ddl
group: Views
order: 1
---

#### Creating & using

```sql
CREATE VIEW active_users AS
SELECT id, name, email FROM users WHERE status = 'active';

SELECT * FROM active_users WHERE name LIKE 'A%';

CREATE MATERIALIZED VIEW sales_summary AS    -- PostgreSQL — physically stored
SELECT product_id, SUM(qty) FROM sales GROUP BY product_id;
REFRESH MATERIALIZED VIEW sales_summary;

DROP VIEW active_users;
```
