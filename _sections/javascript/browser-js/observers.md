---
title: Observers
subtopic: browser-js
group: Observers
order: 1
---

#### IntersectionObserver

```js
const io = new IntersectionObserver((entries) => {
  entries.forEach(entry => { if (entry.isIntersecting) loadImage(entry.target); });
});
io.observe(el);
io.unobserve(el);
```

#### MutationObserver & ResizeObserver

```js
const mo = new MutationObserver((mutations) => {});
mo.observe(el, { childList: true, attributes: true, subtree: true });

const ro = new ResizeObserver((entries) => {});
ro.observe(el);
```
