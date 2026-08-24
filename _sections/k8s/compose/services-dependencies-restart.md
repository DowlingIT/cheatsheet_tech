---
title: Dependencies & Restart Policy
subtopic: compose
group: Services Reference
order: 3
---

#### Startup order & resilience

```yaml
services:
  web:
    depends_on:
      db:
        condition: service_healthy   # waits for db's healthcheck to pass
    restart: unless-stopped            # no | always | on-failure | unless-stopped
```

`depends_on` controls start order only — it does not wait for the app
inside the container to be ready unless you add a `condition`.
