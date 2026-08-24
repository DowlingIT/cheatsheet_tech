---
title: ConfigMaps & Secrets
subtopic: kubernetes
group: Configuration
order: 1
---

#### Creating

```bash
kubectl create configmap app-config --from-literal=LOG_LEVEL=debug
kubectl create configmap app-config --from-file=app.properties
kubectl create secret generic app-secret --from-literal=API_KEY=abc123
```

```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: app-config
data:
  LOG_LEVEL: debug
```
