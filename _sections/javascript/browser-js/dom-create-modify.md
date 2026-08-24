---
title: Create & Modify
subtopic: browser-js
group: DOM Manipulation
order: 1
---

#### Create & insert

```js
const el = document.createElement('div');
el.textContent = 'Hello';        // safe text, no HTML parsing
el.innerHTML = '<b>Hi</b>';        // parses HTML — never with untrusted input
parent.append(el);                   // appends node(s) or strings, end of parent
parent.prepend(el);                    // start of parent
el.before(otherEl);   el.after(otherEl); // insert as siblings
el.remove();
```

#### Clone & replace

```js
const clone = el.cloneNode(true);   // true = deep clone (with children)
el.replaceWith(newEl);
parent.replaceChild(newEl, oldEl);
```
