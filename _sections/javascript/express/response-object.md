---
title: Response Object
subtopic: express
group: Request & Response
order: 2
---

#### Sending a response

```js
res.send('Hello');
res.json({ ok: true });
res.status(404).json({ error: 'Not found' });
res.redirect('/login');
res.render('index', { title: 'Home' });   // needs a view engine
res.set('Cache-Control', 'no-store');
res.cookie('token', value, { httpOnly: true });
```
