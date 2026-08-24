---
title: PL/pgSQL Blocks & Variables
subtopic: pgsql
group: Variables & Control Flow
order: 1
---

#### Anonymous DO block

```sql
DO $$
DECLARE
  total DECIMAL := 0;
BEGIN
  IF total > 50 THEN
    RAISE NOTICE 'Over budget';
  END IF;

  WHILE total < 1000 LOOP
    total := total + 100;
  END LOOP;
END $$;
```
