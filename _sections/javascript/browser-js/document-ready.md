---
title: Document Ready
subtopic: browser-js
group: Window & Document
order: 2
---

#### Loading lifecycle

```js
document.addEventListener('DOMContentLoaded', () => {});  // HTML parsed, DOM ready
window.addEventListener('load', () => {});                   // all resources loaded

document.readyState   // 'loading' | 'interactive' | 'complete'
```

#### Script loading

```html
<script src="a.js" defer></script>   <!-- runs in order, after parsing -->
<script src="b.js" async></script>    <!-- runs ASAP, order not guaranteed -->
```
