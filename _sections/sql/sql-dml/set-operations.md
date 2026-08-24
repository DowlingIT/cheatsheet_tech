---
title: Set Operations
subtopic: sql-dml
group: Joins
order: 2
---

#### Combining result sets

```sql
SELECT name FROM customers
UNION
SELECT name FROM suppliers;        -- combines & dedupes

SELECT name FROM customers
UNION ALL
SELECT name FROM suppliers;        -- combines, keeps duplicates

SELECT id FROM a INTERSECT SELECT id FROM b;   -- rows in both
SELECT id FROM a EXCEPT SELECT id FROM b;        -- rows in a, not in b
```
