---
title: PRAGMA Statements
subtopic: sqlite
group: Pragmas & Introspection
order: 1
---

#### Common pragmas

```sql
PRAGMA table_info(users);        -- columns: name, type, notnull, pk, etc.
PRAGMA foreign_keys = ON;          -- off by default — enable per connection!
PRAGMA journal_mode = WAL;           -- write-ahead logging — better concurrency
PRAGMA integrity_check;
```
