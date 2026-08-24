---
title: Selecting Elements
subtopic: browser-js
group: Selecting & Traversing
order: 1
---

#### Query selectors

```js
document.querySelector('.card')          // first match
document.querySelectorAll('.card')         // static NodeList of all matches
document.getElementById('app')
document.getElementsByClassName('card')      // live HTMLCollection
document.getElementsByTagName('div')
```

#### Scoped & test

```js
el.querySelector('.child')       // search within el only
el.closest('.container')           // nearest matching ancestor (or self)
el.matches('.active')                // test el against a selector, no traversal
```
