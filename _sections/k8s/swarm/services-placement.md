---
title: Placement Constraints & Preferences
subtopic: swarm
group: Services
order: 5
---

#### Controlling which nodes run a task

```bash
docker service create --constraint 'node.role==worker' myapp
docker service create --constraint 'node.labels.disk==ssd' myapp
docker service create --placement-pref 'spread=node.labels.zone' myapp
```

Constraints are a hard filter — the scheduler only considers matching
nodes. Preferences are a soft hint — the scheduler spreads tasks
evenly across the given value instead of excluding anything.
