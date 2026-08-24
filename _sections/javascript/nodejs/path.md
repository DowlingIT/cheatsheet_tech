---
title: path
subtopic: nodejs
group: Path & OS
order: 1
---

#### path

```js
const path = require('path');

path.join('a', 'b', 'c.txt')       // 'a/b/c.txt' — normalizes separators
path.resolve('a', 'b')                // absolute path, resolved from cwd
path.dirname('/a/b/c.txt')              // '/a/b'
path.basename('/a/b/c.txt')               // 'c.txt'
path.extname('/a/b/c.txt')                  // '.txt'
path.parse('/a/b/c.txt')                      // { dir, base, ext, name }
```
