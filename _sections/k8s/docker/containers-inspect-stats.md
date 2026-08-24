---
title: Inspect & Stats
subtopic: docker
group: Containers
order: 4
render_with_liquid: false
---

#### Runtime detail

```bash
docker inspect web                        # full JSON config
docker inspect -f '{{.State.Status}}' web    # single field
docker stats                                   # live CPU/mem/net usage
docker top web                                   # processes inside container
docker port web                                    # published port mappings
```
