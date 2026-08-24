---
title: Advanced Debugging
subtopic: kubernetes
group: Troubleshooting
order: 2
---

#### Ephemeral debug containers & crashed pods

```bash
kubectl debug my-pod -it --image=busybox --target=app  # attach a debug container
kubectl debug node/my-node -it --image=busybox          # debug a node

kubectl logs my-pod --previous                # logs from before the last crash
kubectl get pod my-pod -o jsonpath='{.status.containerStatuses[0].lastState}'
```

```bash
kubectl describe pod my-pod | grep -A5 Events   # scheduling/pull/probe failures
```
