---
title: Dynamic Routes & Layouts
subtopic: nextjs
group: Routing
order: 2
---

#### Dynamic segments

```jsx
// app/posts/[id]/page.js → /posts/1, /posts/2, ...
export default function Post({ params }) {
  return <h1>Post {params.id}</h1>;
}

// app/shop/[...slug]/page.js     — catch-all, /shop/a/b/c
// app/shop/[[...slug]]/page.js   — optional catch-all, also matches /shop
```

#### Layouts

```jsx
export default function PostsLayout({ children }) {
  return <section>{children}</section>;   // wraps every page under posts/
}
```
