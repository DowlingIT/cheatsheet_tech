---
title: Abort & Timeout
subtopic: browser-js
group: Fetch & HTTP
order: 2
---

#### AbortController

```js
const controller = new AbortController();
fetch(url, { signal: controller.signal });
controller.abort();                          // cancels the in-flight request

setTimeout(() => controller.abort(), 5000);    // manual timeout pattern
fetch(url, { signal: AbortSignal.timeout(5000) });  // built-in timeout signal
```
