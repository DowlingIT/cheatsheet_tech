---
title: Replicas & Scaling
subtopic: compose
group: Services Reference
order: 5
---

#### Running multiple copies of a service

```yaml
services:
  worker:
    build: .
    deploy:
      replicas: 3        # default instance count
```

```bash
docker compose up --scale worker=5    # override at runtime
```

A fixed host port (`"8080:80"`) can only bind once — scale a service
past 1 with a port range (`"8080-8090:80"`) or no published port at
all, and give it no `container_name:` (names must be unique per host).
