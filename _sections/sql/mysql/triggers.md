---
title: AFTER Trigger
subtopic: mysql
group: Triggers
order: 1
---

#### CREATE TRIGGER

```sql
DELIMITER $$
CREATE TRIGGER trg_users_audit
AFTER UPDATE ON users
FOR EACH ROW
BEGIN
  INSERT INTO user_audit (user_id, changed_at) VALUES (NEW.id, NOW());
  -- OLD is also available (e.g. OLD.email vs NEW.email)
END $$
DELIMITER ;
```
