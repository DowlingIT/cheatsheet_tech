---
title: Headless Services & Pod DNS
subtopic: kubernetes
group: Networking
order: 4
---

#### Headless Service — no load-balancing, direct pod DNS

```yaml
apiVersion: v1
kind: Service
metadata:
  name: db
spec:
  clusterIP: None       # makes it headless
  selector:
    app: db
  ports:
    - port: 5432
```

#### DNS names

```
<pod>.<service>.<namespace>.svc.cluster.local   # StatefulSet pod, e.g. db-0.db.default...
<service>.<namespace>.svc.cluster.local           # normal ClusterIP Service
```
