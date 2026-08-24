---
title: http Module
subtopic: nodejs
group: HTTP
order: 1
---

#### Minimal server

```js
import http from 'node:http';

const server = http.createServer((req, res) => {
  req.method   req.url   req.headers;
  res.writeHead(200, { 'Content-Type': 'application/json' });
  res.end(JSON.stringify({ ok: true }));
});
server.listen(3000);
```
