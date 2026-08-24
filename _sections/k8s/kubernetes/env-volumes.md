---
title: Env & Volume Mounts
subtopic: kubernetes
group: Configuration
order: 2
---

#### Consuming in a pod

```yaml
containers:
  - name: app
    image: my-app:latest
    envFrom:
      - configMapRef: { name: app-config }
      - secretRef: { name: app-secret }
    env:
      - name: LOG_LEVEL
        valueFrom:
          configMapKeyRef: { name: app-config, key: LOG_LEVEL }
    volumeMounts:
      - name: config-vol
        mountPath: /etc/config
volumes:
  - name: config-vol
    configMap: { name: app-config }
```
