---
title: Ports & Networking Keys
subtopic: compose
group: Services Reference
order: 2
---

#### Service-level networking

```yaml
services:
  web:
    ports:
      - "8080:80"        # host:container
      - "443"             # random host port
    expose:
      - "9000"              # container-to-container only, not published
    networks:
      - frontend
```
