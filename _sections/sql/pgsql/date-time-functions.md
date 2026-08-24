---
title: Date & Time Functions
subtopic: pgsql
group: Built-in Functions
order: 3
---

#### Common functions

```sql
NOW()   CURRENT_DATE   CURRENT_TIMESTAMP
created_at + INTERVAL '7 days'
EXTRACT(YEAR FROM created_at)
AGE(end_date, start_date)              -- interval difference, Postgres-specific
DATE_TRUNC('month', created_at)          -- truncate to a unit: month, week, hour...
```
