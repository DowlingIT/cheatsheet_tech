---
title: Overview
subtopic: sql-ddl
group: Routines & Triggers
order: 1
---

#### Concepts

```
Function       returns a value, usable inside a query — SELECT get_total(id)
Procedure        performs actions, called on its own — CALL do_cleanup()
Trigger            runs automatically on INSERT/UPDATE/DELETE against a table
```

#### Trigger timing

```
BEFORE         fires before the triggering statement — can modify or reject the row
AFTER            fires after — the row is already committed
INSTEAD OF          replaces the statement entirely — mainly used on views
```

T-SQL is the odd one out — it has no `BEFORE` trigger, only `AFTER` (aka `FOR`) and `INSTEAD OF`.

`CREATE FUNCTION`/`CREATE PROCEDURE`/`CREATE TRIGGER` syntax differs significantly per engine — see the T-SQL, PostgreSQL, MySQL, and SQLite pages for concrete examples.
