---
title: Attributes & Classes
subtopic: browser-js
group: DOM Manipulation
order: 2
---

#### Attributes & dataset

```js
el.getAttribute('href')   el.setAttribute('href', url)
el.removeAttribute('disabled')
el.hasAttribute('disabled')
el.dataset.userId               // reads data-user-id
el.dataset.userId = '42';         // writes data-user-id="42"
```

#### classList

```js
el.classList.add('active')
el.classList.remove('active')
el.classList.toggle('active')
el.classList.toggle('active', force)   // explicit on/off
el.classList.contains('active')
```
