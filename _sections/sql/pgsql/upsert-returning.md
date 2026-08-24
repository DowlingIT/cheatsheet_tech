---
title: Upsert & RETURNING
subtopic: pgsql
group: Postgres-Specific Features
order: 2
---

#### ON CONFLICT

```sql
INSERT INTO users (id, name) VALUES (1, 'Alice')
ON CONFLICT (id) DO UPDATE SET name = EXCLUDED.name
RETURNING id, name;

INSERT INTO users (id, name) VALUES (1, 'Alice')
ON CONFLICT (id) DO NOTHING;
```
