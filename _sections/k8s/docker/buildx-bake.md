---
title: Bake
subtopic: docker
group: BuildKit & Buildx
order: 5
---

#### Building multiple targets from one file

```hcl
# docker-bake.hcl
target "app" {
  context    = "."
  dockerfile = "Dockerfile"
  platforms  = ["linux/amd64", "linux/arm64"]
  tags       = ["myapp:1.0"]
}
```

```bash
docker buildx bake              # build every target
docker buildx bake app            # build one target
docker buildx bake --print          # show resolved config, no build
```
