---
title: Triggers
subtopic: sqlite
group: Triggers
order: 1
---

#### CREATE TRIGGER

```sql
CREATE TRIGGER trg_users_audit
AFTER UPDATE ON users
BEGIN
  INSERT INTO user_audit (user_id, changed_at) VALUES (NEW.id, datetime('now'));
  -- OLD.column and NEW.column are both available
END;
```

Triggers are the one procedural-ish feature SQLite fully supports — timing can be `BEFORE`, `AFTER`, or `INSTEAD OF` (the last mainly for views).
