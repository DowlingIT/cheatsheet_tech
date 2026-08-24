---
title: process
subtopic: nodejs
group: Runtime & Process
order: 2
---

#### process

```js
process.argv              // [node, script, ...args]
process.env.NODE_ENV
process.cwd()                // current working directory
process.exit(1)                // exit with a status code
process.platform   process.version
process.on('exit', code => {});
process.on('uncaughtException', err => {});
```
