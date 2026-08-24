---
title: StatefulSets
subtopic: kubernetes
group: Pods & Workloads
order: 4
---

#### Stable identity & per-pod storage

```yaml
apiVersion: apps/v1
kind: StatefulSet
metadata:
  name: db
spec:
  serviceName: db          # must match a headless Service
  replicas: 3
  selector:
    matchLabels: { app: db }
  template:
    metadata:
      labels: { app: db }
    spec:
      containers:
        - name: db
          image: postgres:16
  volumeClaimTemplates:      # one PVC per pod, reused across restarts
    - metadata: { name: data }
      spec:
        accessModes: [ReadWriteOnce]
        resources: { requests: { storage: 10Gi } }
```

```
Pods get fixed names & DNS: db-0, db-1, db-2 (see headless Service card)
Created/scaled/deleted in order, one at a time, by default
```
