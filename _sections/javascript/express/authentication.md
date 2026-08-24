---
title: Authentication
subtopic: express
group: Validation & Auth
order: 2
---

#### Sessions vs JWT

```js
// Sessions (stateful)
const session = require('express-session');
app.use(session({ secret: 'keyboard cat', resave: false, saveUninitialized: false }));

// JWT middleware (stateless)
function auth(req, res, next) {
  const token = req.headers.authorization?.split(' ')[1];
  try {
    req.user = jwt.verify(token, process.env.JWT_SECRET);
    next();
  } catch {
    res.status(401).end();
  }
}
```
