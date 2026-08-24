---
title: Backup, Indexes & Diagnostics
subtopic: sqlite
group: Administration
order: 1
---

#### Backup

```sql
-- CLI: .backup mydb_backup.db     (byte-level copy of the live database)
VACUUM INTO 'backup.db';              -- SQL equivalent — writes a compacted copy
```

#### Index maintenance & diagnostics

```sql
REINDEX;              -- rebuild all indexes (or REINDEX index_name for one)
ANALYZE;                 -- refresh query planner statistics
VACUUM;                     -- reclaim space, defragment the database file

EXPLAIN QUERY PLAN SELECT * FROM orders WHERE status = 'pending';
```

SQLite has no server process to monitor — there's no `PROCESSLIST`/`pg_stat_activity` equivalent, since each connection lives inside the calling application.
