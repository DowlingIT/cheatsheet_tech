---
title: Streams
subtopic: nodejs
group: Streams & Buffers
order: 1
---

#### Readable / Writable

```js
const { createReadStream, createWriteStream } = require('fs');
createReadStream('in.txt').pipe(createWriteStream('out.txt'));

stream.on('data', chunk => {});
stream.on('end', () => {});
stream.on('error', err => {});
```

#### pipeline (preferred — handles errors/cleanup)

```js
import { pipeline } from 'node:stream/promises';
await pipeline(readStream, transformStream, writeStream);
```
