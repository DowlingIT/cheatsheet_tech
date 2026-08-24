---
title: Upsert
subtopic: sqlite
group: SQLite Features
order: 2
---

#### ON CONFLICT (same syntax as PostgreSQL)

```sql
INSERT INTO users (id, name) VALUES (1, 'Alice')
ON CONFLICT (id) DO UPDATE SET name = excluded.name;

INSERT OR REPLACE INTO users (id, name) VALUES (1, 'Alice');   -- older, blunter alternative
```
