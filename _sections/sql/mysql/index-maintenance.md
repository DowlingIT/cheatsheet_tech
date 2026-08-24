---
title: Index Maintenance
subtopic: mysql
group: Administration
order: 2
---

#### Rebuilding & statistics

```sql
OPTIMIZE TABLE users;      -- rebuilds the table & its indexes, reclaims space
ANALYZE TABLE users;         -- refreshes index cardinality statistics
CHECK TABLE users;              -- checks for corruption

SHOW INDEX FROM users;             -- list indexes & their cardinality
```
