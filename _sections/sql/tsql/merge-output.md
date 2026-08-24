---
title: MERGE & OUTPUT
subtopic: tsql
group: Data Modification Extras
order: 1
---

#### MERGE (upsert)

```sql
MERGE INTO users AS target
USING (SELECT 1 AS id, 'Alice' AS name) AS src
ON target.id = src.id
WHEN MATCHED THEN UPDATE SET name = src.name
WHEN NOT MATCHED THEN INSERT (id, name) VALUES (src.id, src.name);
```

#### OUTPUT clause

```sql
DELETE FROM users OUTPUT deleted.id, deleted.email WHERE status = 'inactive';
INSERT INTO users (name) OUTPUT inserted.id VALUES ('Bob');
```
