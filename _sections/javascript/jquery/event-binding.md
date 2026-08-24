---
title: Event Binding
subtopic: jquery
group: Events
order: 1
---

#### Binding events

```js
$el.on('click', handler)
$el.on('click', '.item', handler)     // delegated — binds once, matches future children
$el.off('click', handler)
$el.click(handler)                       // shorthand for common events
$el.trigger('click')                       // fire an event programmatically
```
