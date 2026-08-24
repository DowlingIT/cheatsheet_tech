---
title: INSERT / UPDATE / DELETE
subtopic: sql-dml
group: Data Modification
order: 1
---

#### Modifying rows

```sql
INSERT INTO users (name, email) VALUES ('Alice', 'a@example.com');
INSERT INTO users (name, email) VALUES ('Bob', 'b@x.com'), ('Cara', 'c@x.com');

UPDATE users SET status = 'active' WHERE id = 1;
DELETE FROM users WHERE status = 'inactive';    -- always use WHERE, or it deletes every row
TRUNCATE TABLE logs;                              -- fast delete-all, resets identity
```
