---
title: Pods
subtopic: kubernetes
group: Pods & Workloads
order: 1
---

#### Minimal pod manifest

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: my-app
  labels:
    app: my-app
spec:
  containers:
    - name: app
      image: nginx:1.25
      ports:
        - containerPort: 80
```
