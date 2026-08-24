---
title: Data Types & Identity
subtopic: pgsql
group: Dialect Basics
order: 2
---

#### Postgres type notes

```sql
TEXT   VARCHAR(n)      -- Postgres doesn't distinguish performance-wise — TEXT is fine
SERIAL / BIGSERIAL         -- legacy auto-increment sugar around a sequence
GENERATED ALWAYS AS IDENTITY  -- SQL-standard identity column (preferred since PG 10)
```

#### Identity example

```sql
CREATE TABLE users (
  id   INT GENERATED ALWAYS AS IDENTITY PRIMARY KEY,
  name TEXT
);
```
