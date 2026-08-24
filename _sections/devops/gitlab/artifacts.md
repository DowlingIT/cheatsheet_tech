---
title: Artifacts
subtopic: gitlab
group: Artifacts & Cache
order: 1
---

#### Upload artifacts

```yaml
build:
  script: [npm run build]
  artifacts:
    paths:
      - dist/
      - coverage/
    exclude:
      - dist/**/*.map
    expire_in: 1 week
    when: always            # on_success (default), on_failure, always
```

#### Report artifacts (parsed by GitLab UI)

```yaml
test:
  script: [npm test]
  artifacts:
    reports:
      junit: test-results.xml
      coverage_report:
        coverage_format: cobertura
        path: coverage/cobertura-coverage.xml
      dotenv: build.env
```
