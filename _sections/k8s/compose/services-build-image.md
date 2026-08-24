---
title: Build vs Image
subtopic: compose
group: Services Reference
order: 1
---

#### Where the image comes from

```yaml
services:
  web:
    build:
      context: .
      dockerfile: Dockerfile.dev
      args:
        NODE_ENV: development
  db:
    image: postgres:16          # pulled, not built
```

`build:` and `image:` can combine — Compose tags the built image with `image:`.
