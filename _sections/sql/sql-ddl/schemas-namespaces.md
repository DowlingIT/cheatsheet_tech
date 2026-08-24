---
title: Schemas & Namespaces
subtopic: sql-ddl
group: Altering & Managing Schema
order: 3
---

#### Organizing tables into schemas

```sql
CREATE SCHEMA sales;
CREATE TABLE sales.orders (id SERIAL PRIMARY KEY);    -- schema-qualified name

SET search_path TO sales, public;       -- PostgreSQL — default lookup order
SHOW search_path;
```
