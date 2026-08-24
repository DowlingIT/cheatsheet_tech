---
title: Jobs
subtopic: github
group: Jobs & Steps
order: 1
render_with_liquid: false
---

#### Job structure

{% raw %}
```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    needs: [lint]
    if: github.ref == 'refs/heads/main'
    timeout-minutes: 30
    environment: production
    outputs:
      sha: ${{ steps.vars.outputs.sha }}
    steps: []
```
{% endraw %}

#### Runner options

```yaml
runs-on: ubuntu-latest
runs-on: ubuntu-24.04
runs-on: windows-latest
runs-on: macos-latest
runs-on: [self-hosted, linux, x64]
```
