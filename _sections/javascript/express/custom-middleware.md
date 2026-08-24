---
title: Custom Middleware
subtopic: express
group: Middleware
order: 2
---

#### Writing middleware

```js
function requestLogger(req, res, next) {
  console.log(`${req.method} ${req.url}`);
  next();                          // must call next() or the request hangs
}
app.use(requestLogger);              // applies to every route registered after it

function requireAuth(req, res, next) {
  if (!req.headers.authorization) return res.status(401).end();
  next();
}
app.get('/admin', requireAuth, (req, res) => {});   // per-route middleware
```
