---
title: Rollouts & Rollbacks
subtopic: kubernetes
group: Rollouts & Scaling
order: 1
---

#### Rolling updates

```bash
kubectl set image deployment/my-app app=my-app:v2
kubectl rollout status deployment/my-app
kubectl rollout history deployment/my-app
kubectl rollout undo deployment/my-app                # revert to previous
kubectl rollout undo deployment/my-app --to-revision=2
```
