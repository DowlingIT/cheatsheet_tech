---
title: Images in a Stack
subtopic: swarm
group: Stacks
order: 3
---

#### Pre-built images only

```yaml
services:
  web:
    image: registry.example.com/myapp:1.4.2
    deploy:
      replicas: 3
```

A stack file has no build step — every service must reference an image
already pushed to a registry every node in the cluster can pull from.
Build and `docker push` the image first, then deploy the tag or digest.
