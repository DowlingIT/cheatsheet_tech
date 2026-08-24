---
title: Volumes
subtopic: compose
group: Networking & Volumes
order: 2
---

#### Named volumes

```yaml
services:
  db:
    volumes:
      - dbdata:/var/lib/postgresql/data
      - ./init.sql:/docker-entrypoint-initdb.d/init.sql:ro

volumes:
  dbdata:
    driver: local
```
