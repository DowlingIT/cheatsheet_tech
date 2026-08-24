---
title: Base & Metadata
subtopic: docker
group: Dockerfile Reference
order: 1
---

#### Starting an image

```dockerfile
FROM node:20-slim              # base image
LABEL maintainer="me@example.com"
ARG NODE_ENV=production        # build-time variable
ENV NODE_ENV=$NODE_ENV         # runtime env var (persists in image)
```

`ARG` is only available during build; `ENV` persists into the running container.
