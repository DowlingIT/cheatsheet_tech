---
title: Pod Lifecycle & Hooks
subtopic: kubernetes
group: Probes & Lifecycle
order: 3
---

#### Restart policy & shutdown grace period

```yaml
spec:
  restartPolicy: Always              # Always | OnFailure | Never
  terminationGracePeriodSeconds: 30   # SIGTERM, then SIGKILL after this long
  containers:
    - name: app
      image: my-app:latest
      lifecycle:
        postStart:
          exec: { command: ["sh", "-c", "echo started"] }
        preStop:                       # runs before SIGTERM — e.g. drain connections
          exec: { command: ["sh", "-c", "sleep 5"] }
```

```
Pod phases: Pending -> Running -> Succeeded/Failed
kubectl get pod my-pod -o jsonpath='{.status.phase}'
```
