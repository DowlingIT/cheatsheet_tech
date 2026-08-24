---
title: Procedures
subtopic: pgsql
group: Functions & Procedures
order: 2
---

#### CREATE PROCEDURE (PostgreSQL 11+)

```sql
CREATE PROCEDURE archive_old_orders()
LANGUAGE plpgsql AS $$
BEGIN
  INSERT INTO orders_archive SELECT * FROM orders WHERE created_at < NOW() - INTERVAL '1 year';
  DELETE FROM orders WHERE created_at < NOW() - INTERVAL '1 year';
  COMMIT;                    -- procedures can manage their own transactions
END;
$$;

CALL archive_old_orders();
```
