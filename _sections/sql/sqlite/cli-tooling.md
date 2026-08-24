---
title: sqlite3 CLI
subtopic: sqlite
group: CLI & Tooling
order: 1
---

#### Command-line access

```bash
sqlite3 mydb.db

.tables              -- list tables
.schema users           -- show CREATE TABLE for a table
.mode csv                 -- output format
.import data.csv users      -- import a CSV into a table
.dump                          -- export the whole database as SQL
.quit
```
