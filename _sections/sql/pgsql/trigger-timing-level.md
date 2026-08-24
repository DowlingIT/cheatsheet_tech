---
title: Timing, Level & Events
subtopic: pgsql
group: Triggers
order: 2
---

#### Options

```
BEFORE   AFTER   INSTEAD OF        -- INSTEAD OF is valid only on views
FOR EACH ROW   FOR EACH STATEMENT    -- row: runs per affected row; statement: runs once
```

#### Combining events & TRUNCATE

```sql
CREATE TRIGGER trg_check_stock
BEFORE INSERT OR UPDATE ON order_items    -- combine events with OR
FOR EACH ROW EXECUTE FUNCTION check_stock();

-- TRUNCATE is triggerable too (Postgres-specific) — statement-level only, no per-row NEW/OLD
CREATE TRIGGER trg_log_truncate
AFTER TRUNCATE ON orders
FOR EACH STATEMENT EXECUTE FUNCTION log_truncate();
```
