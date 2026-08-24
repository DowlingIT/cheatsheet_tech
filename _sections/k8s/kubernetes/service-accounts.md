---
title: Service Accounts
subtopic: kubernetes
group: RBAC & Security
order: 3
---

#### Identity for pods talking to the API server

```bash
kubectl create serviceaccount my-app
kubectl get sa
```

```yaml
spec:
  serviceAccountName: my-app          # bind RBAC to this, not the pod itself
  automountServiceAccountToken: false  # opt out if the pod never calls the API
  containers:
    - name: app
      image: my-app:latest
```

```
Every namespace gets a `default` ServiceAccount automatically.
Bind it via a RoleBinding's subjects: [{ kind: ServiceAccount, name, namespace }]
```
