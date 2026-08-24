---
title: Networks
subtopic: docker
group: Networking
order: 1
---

#### Managing networks

```bash
docker network ls
docker network create mynet             # default bridge driver
docker network create --driver overlay swarmnet
docker network connect mynet web
docker network disconnect mynet web
docker network inspect mynet
```
