---
title: Monitoring & Diagnostics
subtopic: mysql
group: Administration
order: 3
---

#### Active connections & queries

```sql
SHOW PROCESSLIST;
SHOW FULL PROCESSLIST;
```

#### Query performance

```sql
SELECT * FROM performance_schema.events_statements_summary_by_digest
ORDER BY sum_timer_wait DESC LIMIT 10;    -- top queries by total time

SHOW VARIABLES LIKE 'slow_query_log%';
SET GLOBAL slow_query_log = 'ON';
```
