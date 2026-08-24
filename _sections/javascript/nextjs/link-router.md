---
title: Link & useRouter
subtopic: nextjs
group: Navigation
order: 1
---

#### Link & programmatic nav

```jsx
import Link from 'next/link';
<Link href="/posts/1" prefetch={false}>View post</Link>;

'use client';
import { useRouter } from 'next/navigation';
const router = useRouter();
router.push('/posts/1');
router.back();
router.refresh();          // re-fetch server data without a full reload
```
