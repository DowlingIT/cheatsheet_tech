---
title: Probes
subtopic: kubernetes
group: Probes & Lifecycle
order: 1
---

#### Liveness, readiness & startup

```yaml
containers:
  - name: app
    image: my-app:latest
    livenessProbe:            # fails -> container is restarted
      httpGet: { path: /healthz, port: 8080 }
      initialDelaySeconds: 5
      periodSeconds: 10
    readinessProbe:            # fails -> pod pulled from Service endpoints
      tcpSocket: { port: 8080 }
      periodSeconds: 5
    startupProbe:                # gates the other two until the app is up
      exec: { command: ["cat", "/tmp/ready"] }
      failureThreshold: 30
      periodSeconds: 2
```
