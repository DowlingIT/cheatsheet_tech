---
title: Server & Client Components
subtopic: nextjs
group: Rendering & Data
order: 1
---

#### Server Components (default)

```jsx
// no directive needed — runs only on the server, never ships to the browser
async function PostList() {
  const posts = await db.posts.findMany();   // direct data access, no API layer
  return <ul>{posts.map(p => <li key={p.id}>{p.title}</li>)}</ul>;
}
```

#### Client Components

```jsx
'use client';   // opt in — needed for hooks, event handlers, browser APIs

import { useState } from 'react';
export default function Counter() {
  const [count, setCount] = useState(0);
  return <button onClick={() => setCount(c => c + 1)}>{count}</button>;
}
```
