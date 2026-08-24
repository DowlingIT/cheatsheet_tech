---
title: App Router Basics
subtopic: nextjs
group: Routing
order: 1
---

#### Pages & nested routes

```jsx
// app/page.js → '/'
export default function Home() { return <h1>Home</h1>; }

// app/about/page.js → '/about'
export default function About() { return <h1>About</h1>; }
```

#### Route groups & private folders

```
(marketing)/about/page.js   parens = route group — doesn't affect the URL
_components/                underscore prefix = opt out of routing
```
