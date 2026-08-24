---
title: Date & Time Functions
subtopic: tsql
group: Built-in Functions
order: 3
---

#### Common functions

```sql
GETDATE()   SYSDATETIME()
DATEDIFF(day, start_date, end_date)
DATEADD(day, 7, order_date)
DATEPART(year, order_date)   YEAR(order_date)   MONTH(order_date)
EOMONTH(order_date)               -- last day of the month
DATEFROMPARTS(2026, 1, 1)
```
