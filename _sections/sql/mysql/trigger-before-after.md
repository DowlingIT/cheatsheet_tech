---
title: BEFORE vs AFTER
subtopic: mysql
group: Triggers
order: 2
---

#### Only BEFORE and AFTER exist — no INSTEAD OF

```sql
DELIMITER $$
CREATE TRIGGER trg_set_defaults
BEFORE INSERT ON users
FOR EACH ROW
BEGIN
  IF NEW.status IS NULL THEN
    SET NEW.status = 'active';    -- BEFORE triggers can modify NEW
  END IF;
END $$
DELIMITER ;
-- AFTER triggers can read NEW/OLD but cannot assign to NEW
```

Each `CREATE TRIGGER` handles exactly one timing + one event. Need a specific firing order between two triggers on the same event? Use `FOLLOWS trg_name` or `PRECEDES trg_name` (5.7.2+).
