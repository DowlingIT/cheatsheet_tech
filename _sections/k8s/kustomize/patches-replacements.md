---
title: Replacements
subtopic: kustomize
group: Patches & Overlays
order: 5
---

#### Copy a field from one resource into another

```yaml
replacements:
  - source:
      kind: Service
      name: my-app
      fieldPath: metadata.name
    targets:
      - select:
          kind: ConfigMap
          name: app-config
        fieldPaths:
          - data.SERVICE_NAME
```

Replaces the deprecated `vars:` field — still common in older examples/blogs,
but `replacements:` is the supported way to wire one resource's value into another.
