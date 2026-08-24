---
title: XMLHttpRequest (Legacy AJAX)
subtopic: browser-js
group: Fetch & HTTP
order: 3
---

#### The original "AJAX" API

```js
const xhr = new XMLHttpRequest();
xhr.open('GET', url);
xhr.onload = () => {
  if (xhr.status >= 200 && xhr.status < 300) console.log(xhr.responseText);
};
xhr.onerror = () => console.error('Request failed');
xhr.send();

xhr.open('POST', url);
xhr.setRequestHeader('Content-Type', 'application/json');
xhr.send(JSON.stringify({ name: 'Alice' }));
```

Prefer `fetch` for new code — XHR mainly shows up in older codebases and upload-progress use cases (`xhr.upload.onprogress`).
