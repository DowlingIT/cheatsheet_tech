---
title: Run Options
subtopic: docker
group: Containers
order: 1
---

#### Common flags

```bash
docker run -d --name web -p 8080:80 nginx        # detached, named, published port
docker run -it ubuntu bash                          # interactive shell
docker run --rm alpine echo hi                        # auto-remove on exit
docker run -e NODE_ENV=prod -v data:/app/data myapp      # env var + volume
docker run --network mynet --restart unless-stopped myapp
```
