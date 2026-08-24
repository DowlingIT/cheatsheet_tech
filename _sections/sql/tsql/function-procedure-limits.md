---
title: Function vs Procedure Limits
subtopic: tsql
group: Stored Procedures & Functions
order: 3
---

#### What each can and can't do

```
Functions (scalar & table-valued)
  MUST return a value — CANNOT modify permanent tables (table variables are OK)
  CANNOT use TRY/CATCH, dynamic SQL, or call non-deterministic built-ins
    like GETDATE() inside a schema-bound function

Procedures
  CAN perform any DML/DDL and manage transactions
  CAN return multiple result sets and use OUTPUT parameters
  CANNOT be used inline inside a SELECT expression — call with EXEC
```

```sql
CREATE FUNCTION dbo.BadIdea(@id INT) RETURNS INT AS
BEGIN
  UPDATE users SET last_seen = GETDATE() WHERE id = @id;  -- ✗ functions can't
  RETURN @id;                                                --   touch real tables
END;
```
