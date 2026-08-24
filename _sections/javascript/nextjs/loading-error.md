---
title: Loading & Error States
subtopic: nextjs
group: Navigation
order: 2
---

#### Streaming UI

```jsx
// app/posts/loading.js — shown automatically while page.js streams in
export default function Loading() { return <Spinner />; }

// app/posts/error.js — must be a Client Component
'use client';
export default function Error({ error, reset }) {
  return <button onClick={() => reset()}>Try again</button>;
}
```
