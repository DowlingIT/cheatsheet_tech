---
title: Ps & Config
subtopic: compose
group: CLI Commands
order: 4
---

#### Inspecting the project

```bash
docker compose ps                  # status of this project's services
docker compose config                # resolved, merged compose.yaml
docker compose config --services       # just the service names
docker compose top                       # processes inside each service
```
