---
title: mysql CLI & Tools
subtopic: mysql
group: CLI & Tooling
order: 1
---

#### Command-line access

```bash
mysql -u root -p mydb
mysql -u root -p -e "SELECT VERSION();"
mysql -u root -p mydb < script.sql

SHOW DATABASES;   SHOW TABLES;   DESCRIBE users;

mysqldump -u root -p mydb > backup.sql
```
