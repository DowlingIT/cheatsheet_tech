---
title: Port Publishing
subtopic: docker
group: Networking
order: 2
---

#### Exposing ports to the host

```bash
docker run -p 8080:80 nginx             # host:container
docker run -p 127.0.0.1:8080:80 nginx     # bind to one host interface
docker run -p 80 nginx                      # random host port
docker run -P nginx                           # publish all EXPOSEd ports
```
