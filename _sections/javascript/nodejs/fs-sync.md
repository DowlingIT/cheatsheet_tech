---
title: fs (Sync)
subtopic: nodejs
group: File System
order: 1
---

#### Synchronous

```js
const fs = require('fs');   // or: import fs from 'node:fs';

fs.readFileSync('file.txt', 'utf8');
fs.writeFileSync('file.txt', 'content');
fs.existsSync('file.txt');
fs.mkdirSync('dir', { recursive: true });
fs.readdirSync('.');
fs.statSync('file.txt').isFile();
```
