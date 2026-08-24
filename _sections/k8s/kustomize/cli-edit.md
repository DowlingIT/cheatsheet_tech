---
title: Edit Commands
subtopic: kustomize
group: CLI Commands
order: 3
---

#### Scripting kustomization.yaml changes

```bash
kustomize edit set image myapp=myapp:2.0
kustomize edit set namespace production
kustomize edit add resource deployment.yaml
kustomize edit add configmap app-config --from-literal=LOG_LEVEL=debug
```

Handy in CI pipelines to bump an image tag without hand-editing YAML.
