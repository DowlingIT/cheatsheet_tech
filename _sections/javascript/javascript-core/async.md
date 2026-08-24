---
title: Async & Promises
subtopic: javascript-core
group: Functions
order: 3
---

#### Promises

```js
const p = new Promise((resolve, reject) => {
  doWork((err, val) => err ? reject(err) : resolve(val));
});
p.then(val => { }).catch(err => { }).finally(() => { });

Promise.all([p1, p2]);          // rejects as soon as any one rejects
Promise.allSettled([p1, p2]);     // waits for all, never rejects
Promise.race([p1, p2]);             // settles as soon as any one settles
```

#### async/await

```js
async function load() {
  try {
    const res = await fetch(url);
    return await res.json();
  } catch (err) {
    console.error(err);
  }
}

await Promise.all(items.map(fetchItem));  // run concurrently, await together
```
