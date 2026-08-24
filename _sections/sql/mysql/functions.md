---
title: Functions
subtopic: mysql
group: Stored Procedures & Functions
order: 2
---

#### CREATE FUNCTION

```sql
DELIMITER $$
CREATE FUNCTION FullName(first VARCHAR(50), last VARCHAR(50))
RETURNS VARCHAR(101)
DETERMINISTIC                     -- required for functions used in generated columns
BEGIN
  RETURN CONCAT(first, ' ', last);
END $$
DELIMITER ;

SELECT FullName('Ada', 'Lovelace');
```
