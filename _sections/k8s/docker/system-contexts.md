---
title: Contexts
subtopic: docker
group: System & Cleanup
order: 4
---

#### Switching between Docker endpoints

```bash
docker context ls
docker context create staging --docker "host=ssh://user@staging-host"
docker context use staging
docker context use default
docker context rm staging
```

Every CLI command runs against whichever context is active — a quick
way to target a remote or cloud engine without exporting `DOCKER_HOST`.
