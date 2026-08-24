---
title: Top-level Keys
subtopic: compose
group: File Structure
order: 2
---

#### What a file can declare

```
services    the containers to run — required
networks    custom networks for services to join
volumes     named volumes for persistent data
configs     non-sensitive config files mounted into services
secrets     sensitive data mounted into services (file-based)
```

`version:` is no longer required in current Compose — the spec is inferred.
