---
title: Identifiers & Syntax Quirks
subtopic: sqlite
group: Dialect Basics
order: 1
---

#### Quoting & concatenation

```sql
SELECT "order" FROM orders;      -- "double quotes" (standard), or [brackets] or `backticks`
SELECT 'Hello' || ' ' || 'World';  -- string concat uses ||, like PostgreSQL
-- Comments: -- single line, /* block */

SELECT * FROM users ORDER BY created_at DESC LIMIT 10 OFFSET 20;
```

SQLite is serverless — the whole database is one file, opened directly by the app, with no separate server process to connect to.
