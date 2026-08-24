---
title: Profiles
subtopic: compose
group: Environment & Profiles
order: 3
---

#### Opt-in services

```yaml
services:
  web:
    build: .
  debug-tools:
    image: busybox
    profiles: ["debug"]
```

```bash
docker compose up                    # debug-tools skipped
docker compose --profile debug up      # debug-tools included
```
