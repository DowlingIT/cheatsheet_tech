---
title: Inspect & History
subtopic: docker
group: Images
order: 4
render_with_liquid: false
---

#### Layers & metadata

```bash
docker inspect myapp:1.0            # full JSON metadata
docker history myapp:1.0              # layer-by-layer build steps
docker image inspect myapp:1.0 --format '{{.Size}}'
```

#### Save & load

```bash
docker save myapp:1.0 -o myapp.tar    # export to tarball
docker load -i myapp.tar                # import from tarball
```
