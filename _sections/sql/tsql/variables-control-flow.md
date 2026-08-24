---
title: Variables & Control Flow
subtopic: tsql
group: Variables & Control Flow
order: 1
---

#### Declaring & branching

```sql
DECLARE @total DECIMAL(10,2) = 0;
SET @total = @total + 100;

IF @total > 50
  PRINT 'Over budget';
ELSE
  PRINT 'OK';

WHILE @total < 1000
BEGIN
  SET @total = @total + 100;
END
```
