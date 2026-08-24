---
title: Data Types & Auto Increment
subtopic: mysql
group: Dialect Basics
order: 2
---

#### Type notes

```sql
TINYINT(1)                              -- conventionally used as boolean
ENUM('small', 'medium', 'large')          -- stored efficiently, validated at insert time
SET('read', 'write', 'admin')               -- multiple values from a fixed list
```

#### Auto-incrementing keys

```sql
CREATE TABLE users (
  id   INT AUTO_INCREMENT PRIMARY KEY,
  name VARCHAR(100)
) ENGINE=InnoDB;                    -- InnoDB (default) supports transactions & FKs

SELECT LAST_INSERT_ID();
```
