---
title: Debugging
subtopic: kubernetes
group: Troubleshooting
order: 1
---

#### Logs, exec & events

```bash
kubectl logs my-pod
kubectl logs my-pod -c my-container   # multi-container pod
kubectl logs -f my-pod                  # follow / stream
kubectl exec -it my-pod -- /bin/sh
kubectl get events --sort-by=.lastTimestamp
kubectl top pods   kubectl top nodes      # resource usage (needs metrics-server)
```
