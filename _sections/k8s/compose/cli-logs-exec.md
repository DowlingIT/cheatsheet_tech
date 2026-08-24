---
title: Logs & Exec
subtopic: compose
group: CLI Commands
order: 2
---

#### Watching & entering services

```bash
docker compose logs                # all services
docker compose logs -f web           # follow one service
docker compose exec web bash           # shell into a running service
docker compose run web npm test          # one-off command, new container
```
