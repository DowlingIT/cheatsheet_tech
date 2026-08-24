---
title: Router Modules
subtopic: express
group: Routing
order: 2
---

#### express.Router()

```js
// routes/users.js
const router = require('express').Router();

router.get('/', getAllUsers);
router.get('/:id', getUser);
router.post('/', createUser);

module.exports = router;

// app.js
app.use('/api/users', require('./routes/users'));   // mounts with a prefix
```
