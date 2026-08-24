---
title: psql & Tools
subtopic: pgsql
group: CLI & Tooling
order: 1
---

#### psql

```bash
psql -h localhost -U postgres -d mydb
psql -c "SELECT version();"

\dt          -- list tables
\d users       -- describe a table
\l               -- list databases
\q                -- quit

pg_dump mydb > backup.sql
```
