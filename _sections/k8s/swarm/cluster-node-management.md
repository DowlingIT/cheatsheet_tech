---
title: Node Management
subtopic: swarm
group: Cluster Management
order: 2
---

#### Listing & scheduling

```bash
docker node ls                        # all nodes in the cluster
docker node inspect worker1 --pretty
docker node update --availability drain worker1   # cordon, no new tasks
docker node update --availability active worker1     # uncordon
```
