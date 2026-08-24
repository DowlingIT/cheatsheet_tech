---
title: Index Maintenance
subtopic: tsql
group: Administration
order: 2
---

#### Rebuild, reorganize & statistics

```sql
ALTER INDEX idx_users_email ON users REBUILD;       -- fully defragments, offline by default
ALTER INDEX idx_users_email ON users REORGANIZE;       -- lighter-weight, always online
ALTER INDEX ALL ON users REBUILD;

UPDATE STATISTICS users;                                   -- refresh query planner stats

SELECT * FROM sys.dm_db_index_physical_stats(DB_ID(), NULL, NULL, NULL, NULL);  -- fragmentation %
```
