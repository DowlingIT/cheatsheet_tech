---
title: Routing Mesh
subtopic: swarm
group: Networking & Secrets
order: 4
---

#### Reaching a service from any node

```bash
docker service create --name web --replicas 3 -p 8080:80 nginx
```

A published port is opened on *every* node in the cluster, not just
the ones running a task — the routing mesh load-balances incoming
connections to a healthy task wherever it happens to be running.

```bash
docker service create --endpoint-mode dnsrr -p 8080:80 nginx
```

`--endpoint-mode dnsrr` opts out of the mesh's virtual IP in favor of
plain round-robin DNS to each task.
