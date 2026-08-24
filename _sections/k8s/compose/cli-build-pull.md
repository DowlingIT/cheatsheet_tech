---
title: Build & Pull
subtopic: compose
group: CLI Commands
order: 3
---

#### Refreshing images

```bash
docker compose build             # build all services with a build: key
docker compose build web           # build just one service
docker compose pull                  # pull latest image: references
docker compose pull --ignore-pull-failures
```
