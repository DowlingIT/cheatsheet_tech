---
title: Views & Templating
subtopic: express
group: Templating & Static Files
order: 1
---

#### Setting a view engine

```js
app.set('view engine', 'ejs');
app.set('views', './views');

app.get('/', (req, res) => {
  res.render('index', { title: 'Home', users });
});
```

```html
<!-- views/index.ejs -->
<h1><%= title %></h1>
<ul><% users.forEach(u => { %><li><%= u.name %></li><% }) %></ul>
```
