---
title: Dynamic PIVOT
subtopic: tsql
group: Querying
order: 3
---

#### Column list built from the data

```sql
DECLARE @cols NVARCHAR(MAX), @sql NVARCHAR(MAX);

SELECT @cols = STRING_AGG(CAST(QUOTENAME(quarter) AS NVARCHAR(MAX)), ', ')
               WITHIN GROUP (ORDER BY quarter)
FROM (SELECT DISTINCT quarter FROM sales) AS q;

SET @sql = N'SELECT product, ' + @cols + N'
FROM (SELECT product, quarter, amount FROM sales) AS src
PIVOT (SUM(amount) FOR quarter IN (' + @cols + N')) AS p;';

EXEC sp_executesql @sql;
```

- `QUOTENAME` brackets each value, so it's a valid identifier and can't inject SQL
- `CAST(... AS NVARCHAR(MAX))` stops `STRING_AGG` failing past 8,000 bytes
- `STRING_AGG` is SQL Server 2017+. Older versions use `STUFF(... FOR XML PATH(''))`
