---
title: Delegation & Custom Events
subtopic: browser-js
group: Events
order: 2
---

#### Event delegation

```js
list.addEventListener('click', (e) => {
  const item = e.target.closest('.item');   // one listener handles every child
  if (!item) return;
  console.log(item.dataset.id);
});
```

#### Custom events

```js
const evt = new CustomEvent('item:selected', { detail: { id: 42 }, bubbles: true });
el.dispatchEvent(evt);
el.addEventListener('item:selected', (e) => console.log(e.detail.id));
```
