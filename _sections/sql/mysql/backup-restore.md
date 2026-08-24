---
title: Backup & Restore
subtopic: mysql
group: Administration
order: 1
---

#### Logical backups

```bash
mysqldump -u root -p mydb > backup.sql
mysqldump -u root -p --all-databases > all_backup.sql
mysql -u root -p mydb < backup.sql             # restore

# Point-in-time recovery from binary logs
mysqlbinlog binlog.000001 | mysql -u root -p
```
