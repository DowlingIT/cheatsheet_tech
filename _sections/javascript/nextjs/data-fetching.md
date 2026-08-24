---
title: Data Fetching & Caching
subtopic: nextjs
group: Rendering & Data
order: 2
---

#### fetch caching

```jsx
fetch(url);                                    // cached indefinitely by default
fetch(url, { cache: 'no-store' });                // no caching — fresh every request
fetch(url, { next: { revalidate: 60 } });           // revalidate every 60s (ISR)
fetch(url, { next: { tags: ['posts'] } });            // tag for on-demand revalidation
```

#### Revalidating on demand

```js
import { revalidatePath, revalidateTag } from 'next/cache';
revalidatePath('/posts');
revalidateTag('posts');
```
