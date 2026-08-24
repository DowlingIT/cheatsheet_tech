---
title: UPSERT & MERGE
subtopic: sql-dml
group: Data Modification
order: 2
---

#### Insert-or-update (syntax varies by engine)

```sql
-- PostgreSQL / SQLite
INSERT INTO users (id, name) VALUES (1, 'Alice')
ON CONFLICT (id) DO UPDATE SET name = EXCLUDED.name;

-- MySQL
INSERT INTO users (id, name) VALUES (1, 'Alice')
ON DUPLICATE KEY UPDATE name = VALUES(name);

-- Standard SQL / SQL Server
MERGE INTO users USING (SELECT 1 AS id, 'Alice' AS name) AS src
ON users.id = src.id
WHEN MATCHED THEN UPDATE SET name = src.name
WHEN NOT MATCHED THEN INSERT (id, name) VALUES (src.id, src.name);
```
