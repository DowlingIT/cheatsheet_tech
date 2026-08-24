---
title: Date & Time Types
subtopic: sql-ddl
group: Data Types
order: 3
---

#### Types

```sql
DATE                                          -- year, month, day only
TIME                                             -- time of day only
TIMESTAMP                                           -- date + time, no time zone
TIMESTAMPTZ / TIMESTAMP WITH TIME ZONE                -- timestamp with an offset
INTERVAL                                                 -- a span of time (PostgreSQL)
```

#### Notes

```
Store timestamps in UTC and convert at the display layer when possible.
MySQL's TIMESTAMP is timezone-aware and range-limited (1970–2038); DATETIME is not.
```
