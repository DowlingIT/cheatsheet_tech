---
title: Validation
subtopic: express
group: Validation & Auth
order: 1
---

#### express-validator

```js
const { body, validationResult } = require('express-validator');

app.post('/users',
  body('email').isEmail(),
  body('age').isInt({ min: 0 }),
  (req, res) => {
    const errors = validationResult(req);
    if (!errors.isEmpty()) return res.status(400).json({ errors: errors.array() });
    // ...
  }
);
```
