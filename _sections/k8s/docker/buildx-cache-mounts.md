---
title: Cache Mounts
subtopic: docker
group: BuildKit & Buildx
order: 3
render_with_liquid: false
---

#### Persisting package caches between builds

```dockerfile
# syntax=docker/dockerfile:1
FROM node:20
WORKDIR /app
COPY package.json .
RUN --mount=type=cache,target=/root/.npm \
    npm install
```

The cache mount persists across builds on the same builder without
being baked into an image layer — the `# syntax=` line at the top
opts into this extended Dockerfile syntax.
