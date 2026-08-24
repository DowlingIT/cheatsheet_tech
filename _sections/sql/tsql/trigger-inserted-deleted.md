---
title: inserted & deleted Tables
subtopic: tsql
group: Triggers
order: 2
---

#### What's in each table, per operation

```
INSERT   inserted has the new rows   —   deleted is empty
DELETE   deleted has the old rows    —   inserted is empty
UPDATE   BOTH are populated: deleted = old values, inserted = new values
```

#### Comparing old vs new on an UPDATE

```sql
CREATE TRIGGER trg_users_track_email
ON users
AFTER UPDATE
AS
BEGIN
  IF UPDATE(email)                          -- did this specific column change?
  BEGIN
    INSERT INTO email_history (user_id, old_email, new_email)
    SELECT i.id, d.email, i.email
    FROM inserted i JOIN deleted d ON i.id = d.id
    WHERE i.email <> d.email;
  END
END;
```
