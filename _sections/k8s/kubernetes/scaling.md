---
title: Scaling & Autoscaling
subtopic: kubernetes
group: Rollouts & Scaling
order: 2
---

#### Manual & auto scaling

```bash
kubectl scale deployment/my-app --replicas=5

kubectl autoscale deployment my-app --min=2 --max=10 --cpu-percent=80
```

```yaml
apiVersion: autoscaling/v2
kind: HorizontalPodAutoscaler
metadata: { name: my-app }
spec:
  scaleTargetRef: { apiVersion: apps/v1, kind: Deployment, name: my-app }
  minReplicas: 2
  maxReplicas: 10
```
