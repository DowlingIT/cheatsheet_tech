---
title: Resource Requests & Limits
subtopic: kubernetes
group: Probes & Lifecycle
order: 2
---

#### Scheduling input vs. hard ceiling

```yaml
containers:
  - name: app
    image: my-app:latest
    resources:
      requests: { cpu: 250m, memory: 128Mi }   # scheduler uses this to place the pod
      limits: { cpu: 500m, memory: 256Mi }       # hard cap — OOMKilled if exceeded
```

```
QoS class     when it applies
Guaranteed    requests == limits for every container, both cpu & memory
Burstable     at least one request/limit set, not equal
BestEffort    no requests or limits set at all — first to be evicted
```
