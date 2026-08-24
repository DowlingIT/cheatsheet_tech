---
title: Global Objects
subtopic: nodejs
group: Runtime & Process
order: 1
---

#### Module-scope globals

```js
__dirname       // absolute path to the current file's directory (CJS only)
__filename        // absolute path to the current file (CJS only)
import.meta.url     // file:// URL of the current module (ESM equivalent)

Buffer   process   require   module   exports
global.foo = 1;   // attaches to the global object — avoid, prefer explicit exports
```
