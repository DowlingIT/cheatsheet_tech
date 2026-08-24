---
title: Identifiers & Syntax Quirks
subtopic: pgsql
group: Dialect Basics
order: 1
---

#### Quoting & concatenation

```sql
SELECT "order", "user id" FROM public."Orders";   -- "double quotes" are case-sensitive
SELECT order_id FROM orders;                          -- unquoted identifiers fold to lowercase
SELECT 'Hello' || ' ' || 'World';                        -- string concat uses ||
-- Comments: -- single line, /* block */

SELECT * FROM users ORDER BY created_at DESC LIMIT 10 OFFSET 20;
```

#### RETURNING clause

```sql
INSERT INTO users (name) VALUES ('Alice') RETURNING id;   -- get generated values back
```
