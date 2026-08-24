---
title: Volumes & Node Affinity
subtopic: swarm
group: Services
order: 6
---

#### Storage follows the node, not the service

```bash
docker service create \
  --mount type=volume,source=dbdata,target=/var/lib/postgresql/data \
  --constraint 'node.hostname==db-node-1' \
  postgres
```

A named volume is local to whichever node the task lands on — the
scheduler can reschedule a task onto a different node with an empty
volume of the same name. Pin stateful services to a specific node with
a constraint, or back the mount with a multi-host volume driver.
