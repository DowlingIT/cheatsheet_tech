---
title: File Structure
subtopic: nextjs
group: Terminology & Structure
order: 2
---

#### Project layout (App Router)

```
app/
  layout.js            root layout — wraps every page, holds <html>/<body>
  page.js               route UI for '/'
  loading.js              loading UI shown while page.js streams in
  error.js                  error boundary for this segment
  not-found.js               404 UI for this segment
  posts/
    [id]/page.js               dynamic route → /posts/:id
    layout.js                    layout for /posts/*
  api/
    posts/route.js                route handler → /api/posts

public/                static assets served from /
next.config.js            build & runtime configuration
middleware.js                runs before a request completes
```
