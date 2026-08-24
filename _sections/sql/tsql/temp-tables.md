---
title: Temp Tables & Table Variables
subtopic: tsql
group: Dialect Basics
order: 3
---

#### #temp vs @tablevar

```sql
CREATE TABLE #results (id INT, total DECIMAL);   -- session-scoped, dropped automatically
INSERT INTO #results SELECT id, SUM(amount) FROM orders GROUP BY id;

DECLARE @nums TABLE (n INT);                       -- table variable — batch/proc scoped,
INSERT INTO @nums VALUES (1), (2), (3);              -- lighter weight, no statistics
```
