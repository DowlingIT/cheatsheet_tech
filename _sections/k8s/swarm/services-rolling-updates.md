---
title: Rolling Updates
subtopic: swarm
group: Services
order: 4
---

#### Controlling rollout behavior

```bash
docker service update \
  --update-parallelism 2 \
  --update-delay 10s \
  --update-failure-action rollback \
  --image myapp:2.0 web

docker service rollback web        # revert to the previous spec
```
