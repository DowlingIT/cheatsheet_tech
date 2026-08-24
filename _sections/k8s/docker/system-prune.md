---
title: Prune Commands
subtopic: docker
group: System & Cleanup
order: 1
---

#### Reclaim disk space

```bash
docker container prune       # remove stopped containers
docker image prune             # remove dangling images
docker image prune -a            # remove all unused images
docker volume prune                # remove unused volumes
docker network prune                 # remove unused networks
docker system prune -a --volumes       # remove everything unused
```
