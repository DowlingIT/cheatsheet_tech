---
title: Error Handling
subtopic: express
group: Error Handling
order: 1
---

#### Error-handling middleware

```js
app.use((err, req, res, next) => {   // 4 args — Express identifies it by arity
  console.error(err.stack);
  res.status(err.status || 500).json({ error: err.message });
});
```

#### Async errors

```js
function asyncHandler(fn) {
  return (req, res, next) => Promise.resolve(fn(req, res, next)).catch(next);
}
app.get('/users', asyncHandler(async (req, res) => {
  const users = await db.users.findMany();   // rejected promises reach the error handler
  res.json(users);
}));
```
