---
title: Overlay Directory Structure
subtopic: kustomize
group: Patches & Overlays
order: 1
---

#### Base + environment overlays

```
base/
  kustomization.yaml
overlays/
  staging/
    kustomization.yaml    # resources: [../../base]
    patch-replicas.yaml
  production/
    kustomization.yaml
    patch-replicas.yaml
```

Each overlay references the shared base and layers its own patches on top.
