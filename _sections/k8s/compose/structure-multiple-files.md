---
title: Multiple Files & Overrides
subtopic: compose
group: File Structure
order: 3
---

#### Layering config

```bash
docker compose -f compose.yaml -f compose.prod.yaml up -d
```

```
compose.yaml            base definition, checked into source control
compose.override.yaml   auto-merged in local dev (loaded by default)
compose.prod.yaml       explicit -f flag, merges over the base file
```

Later files override matching keys; lists like `ports` are replaced, not merged.
