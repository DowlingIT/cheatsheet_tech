---
title: Create a Service
subtopic: swarm
group: Services
order: 1
---

#### Running a replicated service

```bash
docker service create --name web --replicas 3 -p 8080:80 nginx
docker service create --name worker --mode global my-agent
docker service ls
docker service rm web
```

`--mode global` runs exactly one task per node instead of a fixed replica count.
