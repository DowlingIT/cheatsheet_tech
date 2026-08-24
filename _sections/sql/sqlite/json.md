---
title: JSON
subtopic: sqlite
group: SQLite Features
order: 1
---

#### Reading JSON (built-in since 3.38, or the JSON1 extension)

```sql
SELECT json_extract(data, '$.address.city') FROM users;
SELECT data ->> '$.address.city' FROM users;   -- shorthand, like MySQL
SELECT json_valid(data) FROM users;
```
