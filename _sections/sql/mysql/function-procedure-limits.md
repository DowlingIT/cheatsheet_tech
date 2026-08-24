---
title: Function vs Procedure Limits
subtopic: mysql
group: Stored Procedures & Functions
order: 3
---

#### What each can and can't do

```
Functions
  MUST return exactly one value
  MUST be declared DETERMINISTIC or NOT DETERMINISTIC — required for safe
    replication when binary logging is statement-based
  CAN perform DML, but statement-based replication may refuse to log a
    non-deterministic function that writes data

Procedures
  CAN return zero, one, or multiple result sets via SELECT
  Support IN/OUT/INOUT parameters
  No determinism requirement, no restriction on DML
```
