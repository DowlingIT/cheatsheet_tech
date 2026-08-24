---
title: Configs
subtopic: compose
group: Environment & Profiles
order: 5
---

#### Non-sensitive config files

```yaml
configs:
  nginx_conf:
    file: ./nginx.conf

services:
  web:
    configs:
      - source: nginx_conf
        target: /etc/nginx/nginx.conf
```

Like secrets but unencrypted, and readable in `docker compose config`
output — use for config files, not credentials.
