---
title: CREATE TABLE & Constraints
subtopic: sql-ddl
group: Schema Definition
order: 1
---

#### Table definition

```sql
CREATE TABLE users (
  id         SERIAL PRIMARY KEY,             -- or INT AUTO_INCREMENT (MySQL)
  email      VARCHAR(255) NOT NULL UNIQUE,
  age        INT CHECK (age >= 0),
  status     VARCHAR(20) DEFAULT 'active',
  role_id    INT REFERENCES roles(id),        -- foreign key
  created_at TIMESTAMP DEFAULT NOW()
);
```
