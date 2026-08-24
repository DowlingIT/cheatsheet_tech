---
title: AFTER Triggers
subtopic: tsql
group: Triggers
order: 1
---

#### T-SQL has no BEFORE trigger

```sql
-- Only AFTER (aka FOR) and INSTEAD OF exist — there's no BEFORE in T-SQL
CREATE TRIGGER trg_users_audit
ON users
AFTER UPDATE                      -- also valid: AFTER INSERT, UPDATE, DELETE
AS
BEGIN
  INSERT INTO user_audit (user_id, changed_at)
  SELECT id, GETDATE() FROM inserted;
END;
```

```
Multiple events can share one trigger: AFTER INSERT, UPDATE, DELETE
Check which fired with: IF EXISTS(SELECT * FROM inserted) / IF EXISTS(SELECT * FROM deleted)
```
