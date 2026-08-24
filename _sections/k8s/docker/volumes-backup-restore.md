---
title: Backup & Restore
subtopic: docker
group: Volumes & Storage
order: 3
---

#### Using a throwaway container

```bash
# backup
docker run --rm -v data:/data -v $(pwd):/backup alpine \
  tar czf /backup/data.tar.gz -C /data .

# restore
docker run --rm -v data:/data -v $(pwd):/backup alpine \
  tar xzf /backup/data.tar.gz -C /data
```
