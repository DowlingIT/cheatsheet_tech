---
title: Upgrade & Rollback
subtopic: helm
group: Chart Basics
order: 3
---

#### Changing a release in place

```bash
helm upgrade myrelease ./mychart
helm upgrade --install myrelease ./mychart   # install if it doesn't exist yet
helm rollback myrelease 2                      # revert to revision 2
helm rollback myrelease                          # revert to previous revision
```
