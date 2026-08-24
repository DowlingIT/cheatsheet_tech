---
title: Gotchas
subtopic: kustomize
group: CLI Commands
order: 4
---

#### Patches that silently do nothing

```
A patch whose target kind/name (or labelSelector) doesn't match any
resource is skipped without an error. Always eyeball `kustomize build`
output — don't assume a patch landed just because `apply` succeeded.
```

#### Files outside the kustomization root

```bash
# fails by default — kustomize won't read paths above the root
kustomize build overlays/staging

# only if you intentionally need it (CI generators, shared external files)
kustomize build overlays/staging --load-restrictor LoadRestrictionsNone
```
