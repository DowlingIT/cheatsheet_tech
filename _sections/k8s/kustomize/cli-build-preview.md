---
title: Build & Preview
subtopic: kustomize
group: CLI Commands
order: 1
---

#### Rendering final manifests

```bash
kustomize build overlays/staging
kustomize build overlays/staging > rendered.yaml
kustomize build overlays/staging | kubectl diff -f -
```

Always review `build` output before applying — patches can silently miss
their target if `kind`/`name` don't match.
