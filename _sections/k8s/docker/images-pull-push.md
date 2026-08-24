---
title: Pull & Push
subtopic: docker
group: Images
order: 2
---

#### Registry commands

```bash
docker pull nginx:1.25
docker push registry.example.com/myapp:1.0
docker login registry.example.com
docker logout registry.example.com
```

#### Listing & removing

```bash
docker images                     # list local images
docker rmi myapp:1.0                # remove an image
docker rmi $(docker images -q)        # remove all images
```
