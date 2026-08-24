---
title: Variables & Control Flow
subtopic: mysql
group: Variables & Control Flow
order: 1
---

#### Inside a procedure/function

```sql
DELIMITER $$
CREATE PROCEDURE CheckBudget()
BEGIN
  DECLARE total DECIMAL(10,2) DEFAULT 0;

  IF total > 50 THEN
    SELECT 'Over budget';
  END IF;

  WHILE total < 1000 DO
    SET total = total + 100;
  END WHILE;
END $$
DELIMITER ;
```
