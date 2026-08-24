---
title: Trigger Function + AFTER Trigger
subtopic: pgsql
group: Triggers
order: 1
---

#### Trigger function + trigger

```sql
CREATE FUNCTION audit_user_update() RETURNS TRIGGER AS $$
BEGIN
  INSERT INTO user_audit (user_id, changed_at) VALUES (NEW.id, NOW());
  RETURN NEW;   -- OLD is also available for UPDATE/DELETE
END;
$$ LANGUAGE plpgsql;

CREATE TRIGGER trg_users_audit
AFTER UPDATE ON users
FOR EACH ROW EXECUTE FUNCTION audit_user_update();
```
