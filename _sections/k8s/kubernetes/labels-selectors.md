---
title: Labels, Selectors & Annotations
subtopic: kubernetes
group: Labels & Selectors
order: 1
---

#### Labels & selectors

```bash
kubectl label pod my-pod env=prod
kubectl get pods -l env=prod
kubectl get pods -l 'env in (prod, staging)'
kubectl get pods --show-labels
```

#### Labels vs annotations

```
Labels        identify & select resources — what selectors match against
Annotations   arbitrary metadata — not used for selection (docs, tooling hints)
```
