---
title: Inspect & Logs
subtopic: swarm
group: Services
order: 3
---

#### Watching a service

```bash
docker service ps web              # tasks (replicas) & their nodes
docker service inspect web --pretty
docker service logs web              # aggregated across all replicas
docker service logs -f web             # follow
```
