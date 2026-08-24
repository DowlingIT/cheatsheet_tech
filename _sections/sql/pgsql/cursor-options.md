---
title: Cursor Options
subtopic: pgsql
group: Cursors
order: 2
---

#### Declaring with options

```sql
DECLARE cur SCROLL CURSOR FOR SELECT id FROM users;     -- allows FETCH PRIOR/FIRST/LAST
DECLARE cur NO SCROLL CURSOR FOR SELECT id FROM users;     -- forward-only (default)
DECLARE cur INSENSITIVE CURSOR FOR SELECT id FROM users;      -- snapshot as of OPEN time
DECLARE cur CURSOR WITH HOLD FOR SELECT id FROM users;           -- stays open past COMMIT
```
