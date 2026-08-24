---
title: Type Affinity & Dynamic Typing
subtopic: sqlite
group: Dialect Basics
order: 2
---

#### No strict column types (by default)

```sql
CREATE TABLE t (a INT, b TEXT);
INSERT INTO t VALUES ('hello', 42);   -- allowed! SQLite stores whatever you give it

-- Declared type only sets an affinity that nudges storage/comparison:
INTEGER   TEXT   REAL   BLOB   NUMERIC
```

#### Opting into strict types (3.37+)

```sql
CREATE TABLE t (a INT, b TEXT) STRICT;   -- rejects values that don't match the type
```

`AUTOINCREMENT` on an `INTEGER PRIMARY KEY` is rarely needed — plain `INTEGER PRIMARY KEY` already auto-increments and is faster.
