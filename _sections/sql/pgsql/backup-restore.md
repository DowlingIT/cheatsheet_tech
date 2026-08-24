---
title: Backup & Restore
subtopic: pgsql
group: Administration
order: 1
---

#### Logical backups

```bash
pg_dump mydb > backup.sql               # plain SQL, portable & human-readable
pg_dump -Fc mydb > backup.dump            # custom format — required for pg_restore options
pg_restore -d mydb backup.dump
psql mydb < backup.sql                       # restore a plain SQL dump
```

#### Physical backups (for replication / PITR)

```bash
pg_basebackup -D /backups/base -Fp -Xs -P
```
