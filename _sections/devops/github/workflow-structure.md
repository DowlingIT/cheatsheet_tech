---
title: Workflow Structure
subtopic: github
group: Workflows
order: 1
render_with_liquid: false
---

#### File location

`.github/workflows/<name>.yml`

#### Minimal example

```yaml
name: CI
on: push
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: npm ci
      - run: npm test
```

#### Top-level keys

{% raw %}
```yaml
name: CI
on: push
env:
  NODE_ENV: test
permissions:
  contents: read
concurrency:
  group: ${{ github.ref }}
  cancel-in-progress: true
jobs: {}
```
{% endraw %}
