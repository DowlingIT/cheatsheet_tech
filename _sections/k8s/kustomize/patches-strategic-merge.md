---
title: Strategic Merge Patch
subtopic: kustomize
group: Patches & Overlays
order: 2
---

#### Partial resource override

```yaml
# patch-replicas.yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: my-app
spec:
  replicas: 5
```

```yaml
# kustomization.yaml
resources:
  - ../../base
patches:
  - path: patch-replicas.yaml
```

Only the fields you include are merged in — everything else is untouched.
