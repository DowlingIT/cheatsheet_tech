---
title: Build Secrets
subtopic: docker
group: BuildKit & Buildx
order: 4
render_with_liquid: false
---

#### Keeping secrets out of image layers

```dockerfile
# syntax=docker/dockerfile:1
RUN --mount=type=secret,id=npmrc,target=/root/.npmrc \
    npm install
```

```bash
docker buildx build --secret id=npmrc,src=$HOME/.npmrc -t myapp .
```

The secret is available only during that `RUN` step — it never lands
in a layer or the final image, unlike `ARG`/`ENV`.
