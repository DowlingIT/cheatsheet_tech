---
title: Security Context
subtopic: kubernetes
group: RBAC & Security
order: 4
---

#### Pod-level & container-level hardening

```yaml
spec:
  securityContext:              # pod-level — applies to all containers
    runAsUser: 1000
    runAsNonRoot: true
    fsGroup: 2000                # volume ownership
  containers:
    - name: app
      image: my-app:latest
      securityContext:            # container-level overrides pod-level
        allowPrivilegeEscalation: false
        readOnlyRootFilesystem: true
        capabilities:
          drop: ["ALL"]
          add: ["NET_BIND_SERVICE"]
```
