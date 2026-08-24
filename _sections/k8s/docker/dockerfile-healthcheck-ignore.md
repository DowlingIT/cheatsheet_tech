---
title: Healthcheck & .dockerignore
subtopic: docker
group: Dockerfile Reference
order: 4
---

#### Healthcheck

```dockerfile
HEALTHCHECK --interval=30s --timeout=3s \
  CMD curl -f http://localhost:3000/health || exit 1
```

#### .dockerignore

```
node_modules
.git
.env
*.log
dist
```

Keeps the build context small and prevents secrets from leaking into layers.
