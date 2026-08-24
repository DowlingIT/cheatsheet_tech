---
title: Generated Columns & Identity
subtopic: sql-ddl
group: Schema Definition
order: 3
---

#### Auto-incrementing keys (syntax varies by engine)

```sql
id SERIAL PRIMARY KEY                 -- PostgreSQL
id INT AUTO_INCREMENT PRIMARY KEY       -- MySQL
id INT IDENTITY(1,1) PRIMARY KEY          -- SQL Server
```

#### Generated / computed columns

```sql
full_name VARCHAR(200)
  GENERATED ALWAYS AS (first_name || ' ' || last_name) STORED;
```
