---
title: Update & Scale
subtopic: swarm
group: Services
order: 2
---

#### Changing a running service

```bash
docker service scale web=5
docker service update --image nginx:1.25 web
docker service update --env-add LOG_LEVEL=debug web
docker service update --replicas 3 web
```
