---
title: Request Object
subtopic: express
group: Request & Response
order: 1
---

#### Reading the request

```js
req.params.id           // route params — /users/:id
req.query.sort            // query string — ?sort=asc
req.body                    // parsed body (needs express.json())
req.headers['content-type']
req.cookies                    // needs the cookie-parser middleware
req.method   req.path   req.ip
```
