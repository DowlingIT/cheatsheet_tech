---
title: Bind Mounts in Compose
subtopic: compose
group: Networking & Volumes
order: 3
---

#### Live-editing source code

```yaml
services:
  web:
    build: .
    volumes:
      - .:/app                    # bind mount the whole project
      - /app/node_modules           # anonymous volume — keeps container's copy
```

The anonymous volume trick stops the host's `node_modules` (or none at
all) from shadowing the one installed inside the image.
