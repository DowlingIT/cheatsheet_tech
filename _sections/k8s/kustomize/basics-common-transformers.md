---
title: Common Transformers
subtopic: kustomize
group: Kustomization Basics
order: 3
---

#### Applying cross-cutting changes

```yaml
namePrefix: prod-
nameSuffix: "-v2"
namespace: production
labels:                        # preferred over commonLabels/commonAnnotations
  - pairs:
      app.kubernetes.io/env: production
    includeSelectors: false     # true also rewrites matchLabels/selectors
images:
  - name: myapp
    newTag: "2.0"
```

Transformers apply to every resource listed, without editing the originals.
`commonLabels`/`commonAnnotations` still work but never touch selectors —
`labels:` is the newer, more explicit replacement for both.
