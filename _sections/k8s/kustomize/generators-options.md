---
title: Generator Options
subtopic: kustomize
group: Generators
order: 3
---

#### Controlling generated names

```yaml
generatorOptions:
  disableNameSuffixHash: true    # keep a stable name, no content hash
  labels:
    generated-by: kustomize

configMapGenerator:
  - name: app-config
    behavior: merge               # merge | replace | create (default)
    literals:
      - LOG_LEVEL=debug
```

`behavior: merge` lets an overlay add/override keys from a base's generator.
