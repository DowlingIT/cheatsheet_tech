---
title: Cursors
subtopic: pgsql
group: Cursors
order: 1
---

#### Cursor inside a function

```sql
DO $$
DECLARE
  user_cursor CURSOR FOR SELECT id FROM users WHERE status = 'pending';
  user_id INT;
BEGIN
  OPEN user_cursor;
  LOOP
    FETCH user_cursor INTO user_id;
    EXIT WHEN NOT FOUND;
    RAISE NOTICE 'Processing %', user_id;
  END LOOP;
  CLOSE user_cursor;
END $$;
```
