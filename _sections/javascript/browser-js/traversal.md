---
title: Traversal
subtopic: browser-js
group: Selecting & Traversing
order: 2
---

#### Parent, children, siblings

```js
el.parentElement
el.children                        // element children only, not text nodes
el.firstElementChild   el.lastElementChild
el.nextElementSibling   el.previousElementSibling
el.contains(otherEl)                 // true if otherEl is a descendant of el
```
