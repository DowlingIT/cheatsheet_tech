---
title: Timers
subtopic: browser-js
group: Timers & Animation
order: 1
---

#### Timers & frames

```js
const id = setTimeout(() => {}, 1000);
clearTimeout(id);
const interval = setInterval(() => {}, 1000);
clearInterval(interval);
requestAnimationFrame(callback);   // syncs with the browser's repaint cycle
cancelAnimationFrame(id);
```
