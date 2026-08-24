---
title: JSON
subtopic: mysql
group: JSON & XML
order: 1
---

#### Reading & writing JSON columns

```sql
SELECT data->'$.address.city' FROM users;          -- returns a JSON value
SELECT data->>'$.address.city' FROM users;           -- unquoted, returns text (8.0+)
SELECT JSON_EXTRACT(data, '$.address.city') FROM users;

UPDATE users SET data = JSON_SET(data, '$.active', true) WHERE id = 1;
```
