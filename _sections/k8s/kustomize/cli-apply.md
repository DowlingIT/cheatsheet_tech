---
title: Apply with kubectl -k
subtopic: kustomize
group: CLI Commands
order: 2
---

#### Built into kubectl

```bash
kubectl apply -k overlays/staging
kubectl delete -k overlays/staging
kubectl kustomize overlays/staging     # same as `kustomize build`
```

`kubectl -k` uses its bundled Kustomize version, which can lag behind
the standalone `kustomize` CLI.
