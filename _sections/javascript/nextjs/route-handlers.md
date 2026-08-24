---
title: Route Handlers
subtopic: nextjs
group: Server Actions & API
order: 2
---

#### API routes

```js
// app/api/posts/route.js
export async function GET(request) {
  const posts = await db.posts.findMany();
  return Response.json(posts);
}

export async function POST(request) {
  const body = await request.json();
  const post = await db.posts.create(body);
  return Response.json(post, { status: 201 });
}
```
