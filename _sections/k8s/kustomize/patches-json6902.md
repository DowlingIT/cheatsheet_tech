---
title: JSON 6902 Patch
subtopic: kustomize
group: Patches & Overlays
order: 3
---

#### Precise field-level edits

```yaml
# patch-image.yaml
- op: replace
  path: /spec/template/spec/containers/0/image
  value: myapp:2.0
```

```yaml
patches:
  - path: patch-image.yaml
    target:
      kind: Deployment
      name: my-app
```

Use JSON 6902 when you need to `add`/`remove`/`replace` a specific array element.
