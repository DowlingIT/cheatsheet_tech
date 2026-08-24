---
title: Data Types & Identity
subtopic: tsql
group: Dialect Basics
order: 2
---

#### Common types

```sql
NVARCHAR(n)   VARCHAR(n)     -- N-prefixed types store Unicode (UTF-16)
DATETIME2                       -- prefer over DATETIME (higher precision)
BIT                                -- boolean: 0, 1, or NULL
MONEY   DECIMAL(p,s)                  -- MONEY has rounding quirks — DECIMAL is safer
```

#### Identity columns

```sql
CREATE TABLE users (
  id   INT IDENTITY(1,1) PRIMARY KEY,   -- seed 1, increment 1
  name NVARCHAR(100)
);
SELECT SCOPE_IDENTITY();   -- last identity value inserted in this session/scope
```
