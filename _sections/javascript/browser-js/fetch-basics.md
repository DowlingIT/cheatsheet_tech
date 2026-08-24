---
title: Fetch Basics
subtopic: browser-js
group: Fetch & HTTP
order: 1
---

#### GET & POST

```js
const res = await fetch(url);
const data = await res.json();      // or res.text(), res.blob()
res.ok   res.status   res.headers.get('content-type')

await fetch(url, {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({ name: 'Alice' }),
});
```

#### Error handling

```js
async function load() {
  const res = await fetch(url);
  if (!res.ok) throw new Error(`HTTP ${res.status}`);   // fetch never rejects on 404/500
  return res.json();
}
```
