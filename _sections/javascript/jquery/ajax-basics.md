---
title: $.ajax & Shorthand
subtopic: jquery
group: AJAX
order: 1
---

#### $.ajax

```js
$.ajax({
  url: '/api/posts',
  method: 'POST',
  data: { title: 'Hello' },
  success: (data) => console.log(data),
  error: (xhr, status, err) => console.error(err),
});
```

#### Shorthand methods

```js
$.get('/api/posts', (data) => {});
$.post('/api/posts', { title: 'Hello' }, (data) => {});
$.getJSON('/api/posts', (data) => {});
```
