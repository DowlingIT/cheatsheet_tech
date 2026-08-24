---
title: Lifecycle
subtopic: docker
group: Containers
order: 2
---

#### Start, stop, remove

```bash
docker ps                       # running containers
docker ps -a                      # all containers, including stopped
docker stop web                     # graceful stop (SIGTERM, then SIGKILL)
docker start web
docker restart web
docker rm web                         # remove a stopped container
docker rm -f web                        # force remove (running or not)
```
