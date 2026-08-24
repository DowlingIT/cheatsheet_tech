---
title: Patch Targeting
subtopic: kustomize
group: Patches & Overlays
order: 4
---

#### Matching resources by selector

```yaml
patches:
  - path: patch-labels.yaml
    target:
      kind: Deployment
      labelSelector: "tier=frontend"
      namespace: production
```

`target:` can match by `kind`, `name` (supports wildcards), `labelSelector`,
`annotationSelector`, or `namespace` — combine fields to narrow the match.
