---
title: ClusterRole & ClusterRoleBinding
subtopic: kubernetes
group: RBAC & Security
order: 2
---

#### Cluster-wide (or reusable across namespaces)

```yaml
apiVersion: rbac.authorization.k8s.io/v1
kind: ClusterRole
metadata: { name: node-reader }
rules:
  - apiGroups: [""]
    resources: ["nodes"]
    verbs: ["get", "list", "watch"]
---
apiVersion: rbac.authorization.k8s.io/v1
kind: ClusterRoleBinding
metadata: { name: read-nodes }
subjects:
  - kind: User
    name: jane
    apiGroup: rbac.authorization.k8s.io
roleRef: { kind: ClusterRole, name: node-reader, apiGroup: rbac.authorization.k8s.io }
```

```
Role/RoleBinding         namespaced resources, scoped to one namespace
ClusterRole/Binding       cluster-scoped resources, or reused via RoleBinding in many namespaces
```
