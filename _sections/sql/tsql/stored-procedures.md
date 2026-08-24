---
title: Stored Procedures
subtopic: tsql
group: Stored Procedures & Functions
order: 1
---

#### CREATE PROCEDURE

```sql
CREATE PROCEDURE GetUsersByStatus
  @Status VARCHAR(20),
  @Limit  INT = 50            -- default value
AS
BEGIN
  SELECT TOP (@Limit) * FROM users WHERE status = @Status;
END;

EXEC GetUsersByStatus @Status = 'active';
EXEC GetUsersByStatus 'active', 10;
```
