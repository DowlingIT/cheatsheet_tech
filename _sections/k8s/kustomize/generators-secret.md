---
title: secretGenerator
subtopic: kustomize
group: Generators
order: 2
---

#### Generating Secrets

```yaml
secretGenerator:
  - name: db-credentials
    type: Opaque
    envs:
      - db.env
    literals:
      - API_KEY=changeme
```

Prefer `envs:`/`files:` pointing at a `.env` (gitignored) over inline
`literals:` for real credentials.
