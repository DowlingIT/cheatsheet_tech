---
title: Stored Procedures
subtopic: mysql
group: Stored Procedures & Functions
order: 1
---

#### DELIMITER & CREATE PROCEDURE

```sql
DELIMITER $$                        -- redefine the statement terminator temporarily,
CREATE PROCEDURE GetUsersByStatus(     -- so semicolons inside the body don't end it early
  IN p_status VARCHAR(20),
  IN p_limit INT
)
BEGIN
  SELECT * FROM users WHERE status = p_status LIMIT p_limit;
END $$
DELIMITER ;

CALL GetUsersByStatus('active', 10);
```
