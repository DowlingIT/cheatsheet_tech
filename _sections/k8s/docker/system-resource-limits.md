---
title: Resource Limits
subtopic: docker
group: System & Cleanup
order: 3
---

#### Constraining a container

```bash
docker run --memory=512m --cpus=1.5 myapp
docker run --memory=512m --memory-swap=1g myapp
docker update --memory=1g web            # change limits on a running container
```

Without limits, a container can consume all host resources.
