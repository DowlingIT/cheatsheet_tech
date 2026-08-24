---
title: Deploy a Stack
subtopic: swarm
group: Stacks
order: 1
---

#### From a compose file

```bash
docker stack deploy -c docker-compose.yml myapp
docker stack deploy -c docker-compose.yml -c docker-compose.prod.yml myapp
```

A stack groups the services, networks, and volumes defined in one
compose file under a single named unit.
