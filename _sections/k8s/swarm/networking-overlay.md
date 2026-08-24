---
title: Overlay Networks
subtopic: swarm
group: Networking & Secrets
order: 1
---

#### Multi-host networking

```bash
docker network create --driver overlay --attachable myoverlay
docker service create --network myoverlay --name web nginx
```

`--attachable` lets standalone `docker run` containers join the overlay
network too, not just Swarm services.
