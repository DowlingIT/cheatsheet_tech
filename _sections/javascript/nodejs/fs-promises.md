---
title: fs/promises (Async)
subtopic: nodejs
group: File System
order: 2
---

#### Promise-based (preferred)

```js
import { readFile, writeFile, readdir } from 'node:fs/promises';

const content = await readFile('file.txt', 'utf8');
await writeFile('file.txt', 'content');
const entries = await readdir('.', { withFileTypes: true });
```

#### Callback-based (legacy)

```js
fs.readFile('file.txt', 'utf8', (err, data) => {
  if (err) throw err;
});
```
