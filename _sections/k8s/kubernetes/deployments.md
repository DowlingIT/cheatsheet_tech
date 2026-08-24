---
title: Deployments
subtopic: kubernetes
group: Pods & Workloads
order: 2
---

#### Deployment manifest

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: my-app
spec:
  replicas: 3
  selector:
    matchLabels:
      app: my-app
  template:              # pod template — same shape as a Pod's spec
    metadata:
      labels:
        app: my-app
    spec:
      containers:
        - name: app
          image: nginx:1.25
```
