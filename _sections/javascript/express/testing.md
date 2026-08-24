---
title: Testing with Supertest
subtopic: express
group: Testing
order: 1
---

#### Supertest

```js
const request = require('supertest');
const app = require('../app');

test('GET /users returns 200', async () => {
  const res = await request(app).get('/users');
  expect(res.status).toBe(200);
  expect(res.body).toEqual(expect.any(Array));
});
```
