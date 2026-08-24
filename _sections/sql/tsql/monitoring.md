---
title: Monitoring & Diagnostics
subtopic: tsql
group: Administration
order: 3
---

#### Dynamic management views (DMVs)

```sql
SELECT * FROM sys.dm_exec_requests;      -- currently running requests
SELECT * FROM sys.dm_exec_sessions;         -- active sessions/connections
SELECT * FROM sys.dm_os_wait_stats;            -- where time is being spent waiting
SELECT * FROM sys.dm_exec_query_stats;           -- cached plan performance stats
```

#### Per-query diagnostics

```sql
SET STATISTICS IO ON;
SET STATISTICS TIME ON;
SELECT * FROM orders WHERE status = 'pending';   -- now prints reads & duration
```
