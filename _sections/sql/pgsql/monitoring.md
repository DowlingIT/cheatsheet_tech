---
title: Monitoring & Diagnostics
subtopic: pgsql
group: Administration
order: 3
---

#### Activity & stats views

```sql
SELECT * FROM pg_stat_activity;              -- current connections & running queries
SELECT * FROM pg_stat_user_tables;              -- per-table I/O & vacuum/analyze history

EXPLAIN ANALYZE SELECT * FROM orders WHERE status = 'pending';   -- real execution plan
```

#### pg_stat_statements (extension)

```sql
SELECT query, calls, total_exec_time
FROM pg_stat_statements
ORDER BY total_exec_time DESC LIMIT 10;   -- top queries by aggregate time
```
