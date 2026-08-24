---
title: DaemonSets
subtopic: kubernetes
group: Pods & Workloads
order: 5
---

#### One pod per matching node

```yaml
apiVersion: apps/v1
kind: DaemonSet
metadata:
  name: log-agent
spec:
  selector:
    matchLabels: { app: log-agent }
  template:
    metadata:
      labels: { app: log-agent }
    spec:
      containers:
        - name: log-agent
          image: fluent-bit:latest
      tolerations:                  # run on control-plane nodes too if needed
        - effect: NoSchedule
          operator: Exists
```

```
Use cases: log/metrics collectors, node monitoring agents, CNI/CSI node plugins
No replicas: field — the node count decides the pod count
```
