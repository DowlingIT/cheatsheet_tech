---
title: Static Files
subtopic: express
group: Templating & Static Files
order: 2
---

#### express.static

```js
app.use(express.static('public'));                  // /public/logo.png → /logo.png
app.use('/assets', express.static('public'));         // mount under a prefix
app.use(express.static('public', { maxAge: '1d' }));    // set caching headers
```
