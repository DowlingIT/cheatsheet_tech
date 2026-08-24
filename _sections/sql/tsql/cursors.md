---
title: Cursors
subtopic: tsql
group: Cursors
order: 1
---

#### DECLARE / FETCH loop

```sql
DECLARE @id INT;
DECLARE user_cursor CURSOR FOR SELECT id FROM users WHERE status = 'pending';

OPEN user_cursor;
FETCH NEXT FROM user_cursor INTO @id;

WHILE @@FETCH_STATUS = 0
BEGIN
  EXEC ProcessUser @id;
  FETCH NEXT FROM user_cursor INTO @id;
END;

CLOSE user_cursor;
DEALLOCATE user_cursor;
```
