---
title: Identifiers & Syntax Quirks
subtopic: tsql
group: Dialect Basics
order: 1
---

#### Quoting & concatenation

```sql
SELECT [order], [user id] FROM [dbo].[Orders];   -- delimited identifiers use [brackets]
SELECT 'Hello' + ' ' + 'World';                     -- string concat uses +, not ||
-- Comments: -- single line, /* block */

SELECT TOP 10 * FROM users ORDER BY created_at DESC;   -- pagination uses TOP, not LIMIT
SELECT * FROM users ORDER BY id OFFSET 20 ROWS FETCH NEXT 10 ROWS ONLY;
```

#### Batches

```sql
-- GO separates batches sent to the server — not a T-SQL keyword, a client tool feature
CREATE TABLE t (id INT);
GO
INSERT INTO t VALUES (1);
GO
```
