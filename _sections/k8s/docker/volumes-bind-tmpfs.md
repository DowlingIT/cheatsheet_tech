---
title: Bind Mounts & tmpfs
subtopic: docker
group: Volumes & Storage
order: 2
---

#### Host paths & in-memory storage

```bash
docker run -v $(pwd):/app myapp             # bind mount, host:container
docker run -v $(pwd):/app:ro myapp            # read-only bind mount
docker run --tmpfs /app/cache myapp             # in-memory, gone on stop
docker run --mount type=bind,src=$(pwd),dst=/app myapp   # long-form syntax
```
