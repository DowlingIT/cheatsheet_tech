---
title: Functions
subtopic: tsql
group: Stored Procedures & Functions
order: 2
---

#### Scalar & table-valued

```sql
CREATE FUNCTION dbo.FullName(@First NVARCHAR(50), @Last NVARCHAR(50))
RETURNS NVARCHAR(101)
AS
BEGIN
  RETURN @First + ' ' + @Last;
END;
SELECT dbo.FullName('Ada', 'Lovelace');

CREATE FUNCTION dbo.ActiveUsers()
RETURNS TABLE
AS
RETURN (SELECT * FROM users WHERE status = 'active');
SELECT * FROM dbo.ActiveUsers();
```
