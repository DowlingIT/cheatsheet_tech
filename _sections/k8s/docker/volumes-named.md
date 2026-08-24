---
title: Named Volumes
subtopic: docker
group: Volumes & Storage
order: 1
---

#### Managed by Docker

```bash
docker volume create data
docker volume ls
docker volume inspect data
docker run -v data:/app/data myapp        # mount by name
docker volume rm data
docker volume prune                         # remove unused volumes
```

Named volumes are the preferred way to persist data — Docker manages
where they live on disk.
