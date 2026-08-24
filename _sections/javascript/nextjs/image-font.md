---
title: Image & Font
subtopic: nextjs
group: Optimization
order: 1
---

#### next/image

```jsx
import Image from 'next/image';
<Image src="/hero.png" width={800} height={400} alt="Hero" priority />;
// automatic resizing, lazy loading, and format conversion
```

#### next/font

```jsx
import { Inter } from 'next/font/google';
const inter = Inter({ subsets: ['latin'] });
<body className={inter.className}>{children}</body>;   // self-hosted, no layout shift
```
