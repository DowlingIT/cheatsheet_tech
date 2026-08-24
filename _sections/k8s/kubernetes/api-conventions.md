---
title: API Versions & Deprecation
subtopic: kubernetes
group: Extending Kubernetes
order: 3
---

#### Stability tiers in `apiVersion:`

```
v1                     stable — e.g. apps/v1, batch/v1
v1beta1                beta — usually enabled, may still change
v1alpha1                alpha — off by default, no compatibility guarantee
```

```bash
kubectl api-resources                 # which apiVersion each kind is actually served at
kubectl convert -f old.yaml --output-version apps/v1   # requires kubectl-convert plugin
```

```
Deprecated APIs are removed on a schedule (checked at CKAD-relevant version
upgrades) — pin manifests to the non-deprecated apiVersion before upgrading.
```
