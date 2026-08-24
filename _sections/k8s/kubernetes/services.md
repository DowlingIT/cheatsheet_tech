---
title: Services
subtopic: kubernetes
group: Networking
order: 1
---

#### Service types

```yaml
apiVersion: v1
kind: Service
metadata:
  name: my-app
spec:
  selector:
    app: my-app        # routes to pods with this label
  ports:
    - port: 80
      targetPort: 80
  type: ClusterIP       # ClusterIP (default) | NodePort | LoadBalancer
```

#### Quick lookup

```bash
kubectl get svc
kubectl expose deployment my-app --port=80 --type=ClusterIP
kubectl port-forward svc/my-app 8080:80
```
