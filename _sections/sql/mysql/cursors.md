---
title: Cursors
subtopic: mysql
group: Cursors
order: 1
---

#### DECLARE / FETCH loop

```sql
DELIMITER $$
CREATE PROCEDURE ProcessPending()
BEGIN
  DECLARE done INT DEFAULT FALSE;
  DECLARE uid INT;
  DECLARE cur CURSOR FOR SELECT id FROM users WHERE status = 'pending';
  DECLARE CONTINUE HANDLER FOR NOT FOUND SET done = TRUE;

  OPEN cur;
  read_loop: LOOP
    FETCH cur INTO uid;
    IF done THEN LEAVE read_loop; END IF;
    CALL ProcessUser(uid);
  END LOOP;
  CLOSE cur;
END $$
DELIMITER ;
```
