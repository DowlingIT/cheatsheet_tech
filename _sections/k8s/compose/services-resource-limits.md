---
title: Resource Limits
subtopic: compose
group: Services Reference
order: 4
---

#### Constraining a service

```yaml
services:
  web:
    deploy:
      resources:
        limits:
          cpus: "1.0"
          memory: 512M
        reservations:
          memory: 256M
```

`limits` are hard caps enforced by the container runtime. `reservations`
are advisory — a hint for tooling, not an enforced floor.
