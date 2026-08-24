---
title: Cursor Types
subtopic: tsql
group: Cursors
order: 2
---

#### Choosing a type

```sql
DECLARE cur CURSOR FAST_FORWARD FOR SELECT id FROM users;   -- read-only, forward-only,
                                                                 -- optimized — default choice
DECLARE cur CURSOR STATIC FOR SELECT id FROM users;            -- snapshot, insensitive to
                                                                    -- later changes
DECLARE cur CURSOR KEYSET FOR SELECT id FROM users;              -- sees updates to existing
                                                                      -- rows, not new/deleted ones
DECLARE cur CURSOR DYNAMIC FOR SELECT id FROM users;                -- sees all changes live,
                                                                        -- slowest option
DECLARE cur CURSOR SCROLL FOR SELECT id FROM users;                   -- allows FETCH
                                                                          -- PRIOR/FIRST/LAST/ABSOLUTE
```

`FAST_FORWARD` = `FORWARD_ONLY` + `READ_ONLY` — use it unless you specifically need scrolling or to see concurrent changes.
