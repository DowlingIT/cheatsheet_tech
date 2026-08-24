---
title: JSON
subtopic: tsql
group: JSON & XML
order: 1
---

#### Reading & writing

```sql
SELECT * FROM users WHERE ISJSON(data) = 1;
SELECT JSON_VALUE(data, '$.address.city') FROM users;     -- scalar value
SELECT JSON_QUERY(data, '$.address') FROM users;             -- object or array
UPDATE users SET data = JSON_MODIFY(data, '$.active', CAST(1 AS BIT));
```

#### Converting between rows & JSON

```sql
SELECT id, name FROM users FOR JSON PATH, ROOT('users');   -- rows → JSON array
SELECT id, name FROM users FOR JSON AUTO;                     -- infer structure

SELECT * FROM OPENJSON('[{"id":1,"name":"Alice"}]')            -- JSON → rows
WITH (id INT, name NVARCHAR(50));
```
