---
title: Sequences & Temporary Tables
subtopic: sql-ddl
group: Altering & Managing Schema
order: 2
---

#### Sequences

```sql
CREATE SEQUENCE order_number_seq START 1000 INCREMENT 1;
SELECT nextval('order_number_seq');    -- PostgreSQL
```

#### Temporary tables

```sql
CREATE TEMPORARY TABLE tmp_results (id INT, total DECIMAL);   -- dropped at session end
INSERT INTO tmp_results SELECT id, SUM(amount) FROM orders GROUP BY id;
```
