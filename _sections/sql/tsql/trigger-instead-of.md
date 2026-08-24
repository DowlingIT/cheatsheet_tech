---
title: INSTEAD OF Triggers
subtopic: tsql
group: Triggers
order: 3
---

#### Replaces the statement entirely

```sql
-- Commonly used on views to make them "updatable" — the original
-- INSERT/UPDATE/DELETE never actually runs; this body runs in its place
CREATE TRIGGER trg_orders_view_insert
ON vw_orders_with_customer
INSTEAD OF INSERT
AS
BEGIN
  INSERT INTO orders (customer_id, total)
  SELECT customer_id, total FROM inserted;
END;
```

`inserted`/`deleted` are still available here too — they reflect what *would have* been written.
