---
title: DNS & Connecting Containers
subtopic: docker
group: Networking
order: 3
---

#### Service discovery

```
Containers on the same user-defined network resolve each other by name.
docker run --network mynet --name db postgres
docker run --network mynet myapp        # can reach "db" as a hostname
```

The default `bridge` network has no built-in DNS — always create a
user-defined network for name-based discovery.
