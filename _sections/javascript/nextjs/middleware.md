---
title: Middleware
subtopic: nextjs
group: Optimization
order: 2
---

#### middleware.js

```js
// runs before a request completes, at the edge
import { NextResponse } from 'next/server';

export function middleware(request) {
  if (!request.cookies.get('token')) {
    return NextResponse.redirect(new URL('/login', request.url));
  }
  return NextResponse.next();
}

export const config = { matcher: ['/dashboard/:path*'] };
```
