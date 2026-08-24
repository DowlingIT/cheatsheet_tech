---
title: React Router Basics
subtopic: react
group: React Router
order: 1
---

#### Setup & routes

```jsx
import { createBrowserRouter, RouterProvider } from 'react-router-dom';

const router = createBrowserRouter([
  { path: '/', element: <Home /> },
  { path: '/posts/:id', element: <PostDetail /> },
  { path: '*', element: <NotFound /> },
]);

<RouterProvider router={router} />;
```
