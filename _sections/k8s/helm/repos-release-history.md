---
title: Release History
subtopic: helm
group: Repositories & Releases
order: 4
---

#### Tracking revisions

```bash
helm history myrelease
helm status myrelease
helm get manifest myrelease      # rendered manifests currently deployed
```

Every `install`/`upgrade`/`rollback` creates a new numbered revision.
