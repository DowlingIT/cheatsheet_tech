---
title: Inspecting a Chart
subtopic: helm
group: Repositories & Releases
order: 3
---

#### Before you install it

```bash
helm show chart repo/mychart      # Chart.yaml
helm show values repo/mychart       # default values.yaml
helm show readme repo/mychart         # README
helm show crds repo/mychart             # any bundled CRDs
helm show all repo/mychart                # everything above, concatenated
```

Works on a local path (`./mychart`) or a pulled `.tgz` too — no install required.
