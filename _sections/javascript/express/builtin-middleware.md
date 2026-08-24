---
title: Built-in & Third-party Middleware
subtopic: express
group: Middleware
order: 1
---

#### Common middleware

```js
app.use(express.json());                              // parse JSON request bodies
app.use(express.urlencoded({ extended: true }));         // parse form bodies
app.use(express.static('public'));                          // serve static files

const cors = require('cors');
app.use(cors());

const helmet = require('helmet');
app.use(helmet());                          // sets security-related headers

const morgan = require('morgan');
app.use(morgan('dev'));                        // request logging
```
