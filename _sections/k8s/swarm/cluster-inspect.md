---
title: Inspect Cluster
subtopic: swarm
group: Cluster Management
order: 4
render_with_liquid: false
---

#### Cluster-wide state

```bash
docker info                       # includes Swarm section
docker system info --format '{{.Swarm.Nodes}}'
docker node ps                      # tasks running on this node
docker node ps worker1                # tasks on a specific node
```
