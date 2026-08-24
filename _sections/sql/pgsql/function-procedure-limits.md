---
title: Function vs Procedure Limits
subtopic: pgsql
group: Functions & Procedures
order: 3
---

#### What each can and can't do

```
Functions
  CAN perform DML (INSERT/UPDATE/DELETE)
  Run inside the caller's transaction — CANNOT COMMIT or ROLLBACK
  MUST RETURN exactly one value, or a set via RETURNS TABLE / SETOF

Procedures (11+)
  CAN manage transactions — COMMIT/ROLLBACK are allowed inside the body
  Have no return value — use OUT/INOUT parameters instead
  Called with CALL — cannot be used inline inside a SELECT expression
```
