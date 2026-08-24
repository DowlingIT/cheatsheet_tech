---
title: Foreign Keys & Referential Actions
subtopic: sql-ddl
group: Schema Definition
order: 2
---

#### Referential actions

```sql
CREATE TABLE orders (
  id      SERIAL PRIMARY KEY,
  user_id INT REFERENCES users(id)
    ON DELETE CASCADE      -- delete orders when the referenced user is deleted
    ON UPDATE CASCADE,     -- propagate id changes to child rows
  status  VARCHAR(20)
);
```

```
CASCADE                propagate the change to child rows
SET NULL                 set the FK column to NULL
SET DEFAULT                 set the FK column to its default value
RESTRICT / NO ACTION           block the change if matching child rows exist (default)
```
