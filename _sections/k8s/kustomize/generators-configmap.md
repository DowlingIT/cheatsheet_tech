---
title: configMapGenerator
subtopic: kustomize
group: Generators
order: 1
---

#### Generating ConfigMaps from files or literals

```yaml
configMapGenerator:
  - name: app-config
    literals:
      - LOG_LEVEL=info
      - FEATURE_X=true
    files:
      - app.properties
```

Kustomize appends a content hash to the generated name so pods roll on change.
