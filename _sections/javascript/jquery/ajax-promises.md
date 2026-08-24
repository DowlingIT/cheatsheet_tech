---
title: Deferred & Promises
subtopic: jquery
group: AJAX
order: 2
---

#### Deferred / Promise interface

```js
$.ajax('/api/posts')
  .done((data) => console.log(data))
  .fail((err) => console.error(err))
  .always(() => hideSpinner());

$.when($.ajax('/a'), $.ajax('/b')).done((a, b) => {});  // wait for multiple requests
```
