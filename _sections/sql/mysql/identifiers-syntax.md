---
title: Identifiers & Syntax Quirks
subtopic: mysql
group: Dialect Basics
order: 1
---

#### Quoting & concatenation

```sql
SELECT `order`, `user id` FROM `orders`;   -- backticks, not [brackets] or "quotes"
SELECT CONCAT('Hello', ' ', 'World');        -- string concat is a function, not +/||
-- Comments: -- (needs trailing space), # single line, /* block */

SELECT * FROM users ORDER BY created_at DESC LIMIT 10 OFFSET 20;
SELECT * FROM users LIMIT 20, 10;            -- shorthand: LIMIT offset, count
```

Table/column name case-sensitivity depends on the OS and `lower_case_table_names` setting — Linux is case-sensitive by default, Windows/macOS usually aren't.
