---
title: Web Storage & Cookies
subtopic: browser-js
group: Storage
order: 1
---

#### localStorage / sessionStorage

```js
localStorage.setItem('token', 'abc123');
localStorage.getItem('token');
localStorage.removeItem('token');
localStorage.clear();
localStorage.setItem('user', JSON.stringify(user));   // objects need serializing
JSON.parse(localStorage.getItem('user'));
```

#### Cookies

```js
document.cookie = 'theme=dark; max-age=3600; path=/';
document.cookie;               // returns ALL cookies as one string — parse manually
```
