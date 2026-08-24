---
title: String Functions
subtopic: sql-dml
group: Built-in Functions
order: 1
---

#### Common functions (names & concat operator vary by engine)

```sql
CONCAT(first_name, ' ', last_name)     -- or first_name || ' ' || last_name
UPPER(name)   LOWER(name)   TRIM(name)
LENGTH(name)                              -- LEN() in T-SQL
SUBSTRING(name FROM 1 FOR 3)                -- or SUBSTRING(name, 1, 3)
REPLACE(name, 'a', 'b')
```

See the T-SQL, PostgreSQL, MySQL, and SQLite pages for each engine's full function names.
