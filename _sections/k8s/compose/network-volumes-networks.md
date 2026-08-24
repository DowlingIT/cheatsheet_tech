---
title: Networks
subtopic: compose
group: Networking & Volumes
order: 1
---

#### Custom networks

```yaml
services:
  web:
    networks:
      - frontend
  db:
    networks:
      - backend

networks:
  frontend:
  backend:
    driver: bridge
```

Every project gets a default network automatically — declare `networks:`
only when you need to isolate services from each other.
