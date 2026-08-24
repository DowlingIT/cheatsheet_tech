---
title: No Stored Procedures, Functions, or Cursors
subtopic: sqlite
group: What's Not Supported
order: 1
---

#### What SQLite doesn't have

```
Stored procedures    not supported — there's no CALL, no procedural SQL blocks
User-defined functions  not definable in SQL — registered via the host language's API
                            (e.g. sqlite3_create_function in C, conn.create_function in Python)
Cursors                  not exposed to SQL — the host language's driver iterates result rows
XML                        no built-in XML functions — JSON (built-in since 3.38) covers
                              the structured-data use case instead
```

SQLite is intentionally minimal: control flow, procedures, and business logic live in the
application, not the database. This keeps it embeddable and dependency-free.
