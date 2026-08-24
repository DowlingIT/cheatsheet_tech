---
title: Error Handling
subtopic: mysql
group: Error Handling
order: 1
---

#### DECLARE HANDLER & SIGNAL

```sql
DELIMITER $$
CREATE PROCEDURE SafeTransfer()
BEGIN
  DECLARE EXIT HANDLER FOR SQLEXCEPTION
  BEGIN
    ROLLBACK;
    RESIGNAL;
  END;

  START TRANSACTION;
  IF (SELECT balance FROM accounts WHERE id = 1) < 100 THEN
    SIGNAL SQLSTATE '45000' SET MESSAGE_TEXT = 'Insufficient funds';
  END IF;
  COMMIT;
END $$
DELIMITER ;
```
