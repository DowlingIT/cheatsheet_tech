---
title: UPDATE OF & WHEN
subtopic: sqlite
group: Triggers
order: 2
---

#### Firing only on specific columns/conditions

```sql
CREATE TRIGGER trg_track_status
AFTER UPDATE OF status ON orders          -- fires only when the status column changes,
                                             -- not on every UPDATE to the row
WHEN NEW.status = 'cancelled'                -- optional condition — skipped otherwise
BEGIN
  INSERT INTO cancellations (order_id, cancelled_at) VALUES (NEW.id, datetime('now'));
END;
```
