---
title: Leave & Demote
subtopic: swarm
group: Cluster Management
order: 3
---

#### Changing membership

```bash
docker node promote worker1          # worker -> manager
docker node demote worker1             # manager -> worker
docker node rm worker1                   # remove a down/drained node
docker swarm leave                         # leave the cluster (run on the node)
docker swarm leave --force                   # force-leave a manager
```
