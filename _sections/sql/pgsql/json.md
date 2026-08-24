---
title: JSON & JSONB
subtopic: pgsql
group: JSON & XML
order: 1
---

#### Reading & writing

```sql
SELECT data->'address'->>'city' FROM users;    -- -> returns JSON, ->> returns text
SELECT * FROM users WHERE data @> '{"active": true}';   -- containment operator
CREATE INDEX idx_users_data ON users USING GIN (data);    -- index JSONB for lookups
```

#### JSON vs JSONB

```
JSON     stores the exact text — preserves key order & whitespace, no indexing
JSONB      stores a parsed binary form — faster to query, supports GIN indexes;
             prefer this unless you need to preserve the original text exactly
```
