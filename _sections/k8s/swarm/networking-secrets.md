---
title: Secrets
subtopic: swarm
group: Networking & Secrets
order: 2
---

#### Encrypted at rest, mounted in memory

```bash
echo "supersecret" | docker secret create db_password -
docker secret ls
docker service create --secret db_password postgres
```

Inside the container, secrets are mounted read-only at `/run/secrets/<name>`.
