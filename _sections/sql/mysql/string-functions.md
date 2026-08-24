---
title: String Functions
subtopic: mysql
group: Built-in Functions
order: 1
---

#### Common functions

```sql
CONCAT(first, ' ', last)
LENGTH(name)                       -- byte length — use CHAR_LENGTH() for character count
SUBSTRING(name, 1, 3)
UPPER(name)   LOWER(name)   TRIM(name)
REPLACE(name, 'a', 'b')
GROUP_CONCAT(name SEPARATOR ', ')     -- aggregate concat
```
