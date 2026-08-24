---
title: Buildx Setup
subtopic: docker
group: BuildKit & Buildx
order: 1
---

#### Builder instances

```bash
docker buildx ls                          # list builders
docker buildx create --use --name mybuilder --bootstrap
docker buildx inspect --bootstrap
docker buildx use mybuilder
docker buildx rm mybuilder
```

BuildKit is the default build engine since Docker 23 — `buildx` adds
multiple, switchable builder instances on top of it.
