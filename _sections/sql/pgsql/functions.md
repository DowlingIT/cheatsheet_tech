---
title: Functions
subtopic: pgsql
group: Functions & Procedures
order: 1
---

#### CREATE FUNCTION

```sql
CREATE FUNCTION full_name(first TEXT, last TEXT)
RETURNS TEXT AS $$
BEGIN
  RETURN first || ' ' || last;
END;
$$ LANGUAGE plpgsql;

SELECT full_name('Ada', 'Lovelace');
```
