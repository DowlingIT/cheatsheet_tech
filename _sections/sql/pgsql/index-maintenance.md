---
title: Index Maintenance
subtopic: pgsql
group: Administration
order: 2
---

#### Rebuilding & statistics

```sql
REINDEX INDEX idx_users_email;
REINDEX TABLE users;
REINDEX TABLE CONCURRENTLY users;      -- rebuild without locking out writes (12+)

VACUUM users;             -- reclaim space from dead rows
VACUUM ANALYZE users;       -- also refresh planner statistics
ANALYZE users;
```
