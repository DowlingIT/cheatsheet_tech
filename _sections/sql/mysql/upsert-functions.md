---
title: Upsert & Common Functions
subtopic: mysql
group: MySQL-Specific Features
order: 1
---

#### ON DUPLICATE KEY UPDATE

```sql
INSERT INTO users (id, name) VALUES (1, 'Alice')
ON DUPLICATE KEY UPDATE name = VALUES(name);
```

#### Handy functions

```sql
IFNULL(nickname, 'Unknown')          -- MySQL's 2-argument COALESCE shorthand
GROUP_CONCAT(name SEPARATOR ', ')      -- concatenate grouped rows into one string
IF(age >= 18, 'adult', 'minor')          -- inline conditional
```
