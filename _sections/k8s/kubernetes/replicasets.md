---
title: ReplicaSets
subtopic: kubernetes
group: Pods & Workloads
order: 3
---

#### Rarely created directly — Deployments own one for you

```yaml
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: my-app-rs
spec:
  replicas: 3
  selector:
    matchLabels:
      app: my-app
  template:
    metadata:
      labels:
        app: my-app
    spec:
      containers:
        - name: app
          image: nginx:1.25
```

```bash
kubectl get rs
kubectl get rs -o wide --show-labels    # see which Deployment owns each
```
