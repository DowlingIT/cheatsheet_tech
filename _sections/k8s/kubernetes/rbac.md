---
title: RBAC Basics
subtopic: kubernetes
group: RBAC & Security
order: 1
---

#### Role & RoleBinding

```yaml
apiVersion: rbac.authorization.k8s.io/v1
kind: Role
metadata: { name: pod-reader, namespace: default }
rules:
  - apiGroups: [""]
    resources: ["pods"]
    verbs: ["get", "list", "watch"]
---
apiVersion: rbac.authorization.k8s.io/v1
kind: RoleBinding
metadata: { name: read-pods, namespace: default }
subjects:
  - kind: ServiceAccount
    name: my-app
roleRef: { kind: Role, name: pod-reader, apiGroup: rbac.authorization.k8s.io }
```
