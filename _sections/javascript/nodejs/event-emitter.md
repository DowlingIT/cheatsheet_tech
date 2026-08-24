---
title: EventEmitter
subtopic: nodejs
group: Events & Processes
order: 1
---

#### EventEmitter

```js
const { EventEmitter } = require('events');

class MyEmitter extends EventEmitter {}
const emitter = new MyEmitter();

emitter.on('event', (a, b) => {});
emitter.once('event', handler);      // fires once, then auto-removes
emitter.emit('event', 1, 2);
emitter.off('event', handler);
```
