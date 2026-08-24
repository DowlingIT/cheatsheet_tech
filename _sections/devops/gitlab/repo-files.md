---
title: Repository Files
subtopic: gitlab
group: Runners & Repo
order: 1
---

#### .gitlab folder

```
.gitlab/
  CODEOWNERS                    → reviewer assignments
  issue_templates/
    bug.md
    feature.md
  merge_request_templates/
    default.md
```

#### CODEOWNERS

```
# .gitlab/CODEOWNERS

[Backend]
src/api/          @alice @bob
*.go              @org/backend-team

[Frontend]
src/ui/           @org/frontend-team
```

#### Container registry login in CI

```yaml
before_script:
  - docker login -u $CI_REGISTRY_USER \
      -p $CI_REGISTRY_PASSWORD $CI_REGISTRY

script:
  - docker build -t $CI_REGISTRY_IMAGE:$CI_COMMIT_SHORT_SHA .
  - docker push $CI_REGISTRY_IMAGE:$CI_COMMIT_SHORT_SHA
```
