---
title: CRDs & Operators
subtopic: kubernetes
group: Extending Kubernetes
order: 1
---

#### CustomResourceDefinition — teach the API a new kind

```yaml
apiVersion: apiextensions.k8s.io/v1
kind: CustomResourceDefinition
metadata: { name: backups.example.com }
spec:
  group: example.com
  names: { kind: Backup, plural: backups }
  scope: Namespaced
  versions:
    - name: v1
      served: true
      storage: true
      schema: { openAPIV3Schema: { type: object } }
```

```
Operator = CRD + a controller that watches those custom objects and drives
real state toward spec (e.g. a Backup CR -> the operator actually runs one).
Reconcile loop: observe -> diff against spec -> act -> repeat.
```
