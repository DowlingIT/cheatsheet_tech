---
title: Configs
subtopic: swarm
group: Networking & Secrets
order: 3
---

#### Non-sensitive config files

```bash
docker config create nginx_conf ./nginx.conf
docker config ls
docker service create \
  --config source=nginx_conf,target=/etc/nginx/nginx.conf \
  nginx
```

Like secrets but unencrypted — use for config files, not credentials.
