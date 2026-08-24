---
title: Text & Binary Types
subtopic: sql-ddl
group: Data Types
order: 2
---

#### Text types

```sql
CHAR(n)          -- fixed-length, space-padded
VARCHAR(n)         -- variable-length, max n characters
TEXT                 -- variable-length, no practical length limit
```

#### Binary types & collation

```sql
BLOB / BYTEA           -- raw binary data (BYTEA is PostgreSQL's name for it)
VARBINARY(n)              -- variable-length binary (SQL Server / MySQL)

-- Collation controls sort order & case sensitivity, set per column or database
name VARCHAR(100) COLLATE "en_US"   -- syntax varies significantly by engine
```
