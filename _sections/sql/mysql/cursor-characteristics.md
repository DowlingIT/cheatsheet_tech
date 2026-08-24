---
title: Cursor Characteristics
subtopic: mysql
group: Cursors
order: 2
---

#### One behavior only

```
Read-only        cannot UPDATE/DELETE through the cursor
Asensitive          may or may not reflect concurrent changes to the underlying data
Forward-only            no FETCH PRIOR — NEXT is the only direction available
```

Unlike T-SQL's `FAST_FORWARD`/`STATIC`/`KEYSET`/`DYNAMIC` choice, MySQL cursors don't have variants — every cursor behaves this way.
