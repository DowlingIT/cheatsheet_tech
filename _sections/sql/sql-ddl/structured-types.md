---
title: Structured & Special Types
subtopic: sql-ddl
group: Data Types
order: 4
---

#### Structured types (support varies by engine)

```sql
JSON / JSONB                    -- structured data; JSONB (Postgres) is binary & indexed
XML                                 -- native type in PostgreSQL & SQL Server only —
                                       -- MySQL/SQLite store it as TEXT and use functions
ARRAY[1, 2, 3]                        -- native arrays (PostgreSQL)
UUID                                     -- universally unique identifier
ENUM('small', 'medium', 'large')           -- fixed set of string values (MySQL/PostgreSQL)
```

JSON and XML query/manipulation functions differ significantly per engine — see the T-SQL, PostgreSQL, and MySQL pages for concrete syntax.
