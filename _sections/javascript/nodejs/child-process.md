---
title: child_process
subtopic: nodejs
group: Events & Processes
order: 2
---

#### Running commands

```js
const { exec, spawn } = require('child_process');

exec('ls -la', (err, stdout, stderr) => {});    // buffers full output at once

const child = spawn('ls', ['-la']);              // streams output incrementally
child.stdout.on('data', chunk => {});
child.on('close', code => {});
```
