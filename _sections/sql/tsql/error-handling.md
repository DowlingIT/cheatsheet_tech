---
title: TRY/CATCH
subtopic: tsql
group: Error Handling
order: 1
---

#### Structured error handling

```sql
BEGIN TRY
  UPDATE accounts SET balance = balance - 100 WHERE id = 1;
  IF @@ROWCOUNT = 0 THROW 50001, 'Account not found', 1;
END TRY
BEGIN CATCH
  PRINT ERROR_MESSAGE();
  PRINT ERROR_NUMBER();
  ROLLBACK TRANSACTION;
END CATCH;
```
