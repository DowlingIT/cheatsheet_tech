---
title: Exception Handling
subtopic: pgsql
group: Error Handling
order: 1
---

#### BEGIN / EXCEPTION

```sql
DO $$
BEGIN
  UPDATE accounts SET balance = balance - 100 WHERE id = 1;
  IF NOT FOUND THEN
    RAISE EXCEPTION 'Account % not found', 1;
  END IF;
EXCEPTION
  WHEN OTHERS THEN
    RAISE NOTICE 'Error: %', SQLERRM;
END $$;
```
