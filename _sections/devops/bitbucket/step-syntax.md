---
title: Step Syntax
subtopic: bitbucket
group: Steps & Caches
order: 1
---

#### Step options

```yaml
- step:
    name: Deploy
    image: node:20          # override global image
    runs-on:
      - self.hosted
      - linux
    trigger: manual         # requires UI click to proceed
    deployment: production
    size: 2x                # 2x memory/CPU
    max-time: 30            # minutes before timeout
    script:
      - npm run deploy
    after-script:           # always runs, even on failure
      - ./notify.sh $BITBUCKET_EXIT_CODE
```

#### Parallel steps

```yaml
- parallel:
    - step:
        name: Unit Tests
        script: [npm run test:unit]
    - step:
        name: Lint
        script: [npm run lint]
    - step:
        name: Type Check
        script: [npm run typecheck]
```
