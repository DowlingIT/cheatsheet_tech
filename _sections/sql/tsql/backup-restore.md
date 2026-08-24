---
title: Backup & Restore
subtopic: tsql
group: Administration
order: 1
---

#### Backing up

```sql
BACKUP DATABASE MyDb TO DISK = 'C:\Backups\MyDb.bak';
BACKUP DATABASE MyDb TO DISK = 'C:\Backups\MyDb_diff.bak' WITH DIFFERENTIAL;
BACKUP LOG MyDb TO DISK = 'C:\Backups\MyDb.trn';           -- transaction log backup
```

#### Restoring

```sql
RESTORE DATABASE MyDb FROM DISK = 'C:\Backups\MyDb.bak' WITH REPLACE;
RESTORE VERIFYONLY FROM DISK = 'C:\Backups\MyDb.bak';        -- check the backup is valid
```
