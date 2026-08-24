---
title: Date & Time Functions
subtopic: sqlite
group: Built-in Functions
order: 3
---

#### Common functions (no native date type — stored as TEXT/REAL/INTEGER)

```sql
SELECT date('now');                     -- '2026-08-18'
SELECT datetime('now', '+7 days');
SELECT strftime('%Y-%m', created_at) FROM orders;
SELECT julianday('now') - julianday(start_date);   -- difference in days
```
