---
title: Up & Down
subtopic: compose
group: CLI Commands
order: 1
---

#### Starting & stopping the stack

```bash
docker compose up                    # foreground, all services
docker compose up -d                   # detached
docker compose up -d --build             # rebuild images first
docker compose down                        # stop & remove containers/networks
docker compose down -v                       # also remove named volumes
```
