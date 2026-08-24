---
title: Base Directory Structure
subtopic: kustomize
group: Kustomization Basics
order: 2
---

#### A typical base

```
base/
  kustomization.yaml
  deployment.yaml
  service.yaml
  configmap.yaml
```

A "base" is any directory with a `kustomization.yaml` — it can be
referenced by overlays via a relative or Git path.
