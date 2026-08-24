---
title: Build & Tag
subtopic: docker
group: Images
order: 1
---

#### Build an image

```bash
docker build -t myapp:1.0 .                 # build from Dockerfile in cwd
docker build -t myapp:1.0 -f Dockerfile.dev .   # custom Dockerfile
docker build --no-cache -t myapp:1.0 .        # skip layer cache
docker build --build-arg NODE_ENV=prod -t myapp .
```

#### Tag & rename

```bash
docker tag myapp:1.0 myapp:latest
docker tag myapp:1.0 registry.example.com/myapp:1.0
```
