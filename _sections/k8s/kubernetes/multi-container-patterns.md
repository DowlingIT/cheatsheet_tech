---
title: Multi-container Patterns
subtopic: kubernetes
group: Pods & Workloads
order: 6
---

#### Init containers — run to completion before app containers start

```yaml
spec:
  initContainers:
    - name: wait-for-db
      image: busybox
      command: ["sh", "-c", "until nc -z db 5432; do sleep 1; done"]
  containers:
    - name: app
      image: my-app:latest
```

#### Sidecars — run alongside the main container, same pod network/storage

```yaml
  containers:
    - name: app
      image: my-app:latest
    - name: log-shipper       # sidecar: shares volumes/network with app
      image: fluent-bit:latest
```
