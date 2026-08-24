---
title: sqlcmd & Tools
subtopic: tsql
group: CLI & Tooling
order: 1
---

#### Command-line access

```bash
sqlcmd -S localhost -U sa -P password -d MyDb
sqlcmd -S localhost -Q "SELECT @@VERSION"
sqlcmd -S localhost -d MyDb -i script.sql

bcp MyDb.dbo.Users out users.csv -S localhost -U sa -P password -c -t,
```

SQL Server Management Studio (SSMS) and Azure Data Studio are the common GUI tools.
