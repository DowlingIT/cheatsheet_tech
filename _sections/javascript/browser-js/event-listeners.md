---
title: Event Listeners
subtopic: browser-js
group: Events
order: 1
---

#### Listening

```js
el.addEventListener('click', handler);
el.addEventListener('click', handler, { once: true });     // auto-removes after firing
el.addEventListener('click', handler, { capture: true });    // capture phase
el.removeEventListener('click', handler);                      // needs the same fn reference
```

#### Event object

```js
function handler(e) {
  e.target;              // element that triggered the event
  e.currentTarget;         // element the listener is attached to
  e.preventDefault();        // stop the default action (e.g. form submit)
  e.stopPropagation();         // stop bubbling to ancestors
}
```
