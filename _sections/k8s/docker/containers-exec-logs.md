---
title: Exec & Logs
subtopic: docker
group: Containers
order: 3
---

#### Getting inside & watching output

```bash
docker exec -it web bash          # shell into a running container
docker exec web ls /app             # run a one-off command
docker logs web                       # print logs
docker logs -f web                      # follow logs
docker logs --tail 100 web                # last 100 lines
docker cp web:/app/log.txt ./log.txt        # copy a file out
```
