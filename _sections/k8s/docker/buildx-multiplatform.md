---
title: Multi-platform Builds
subtopic: docker
group: BuildKit & Buildx
order: 2
---

#### Building for more than one architecture

```bash
docker buildx build --platform linux/amd64,linux/arm64 -t myapp:1.0 --push .
```

Multi-platform output can't be loaded into the local image store —
use `--push` to send it straight to a registry, or drop to one
`--platform` and add `--load` to keep the result local.
