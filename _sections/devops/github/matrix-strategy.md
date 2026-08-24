---
title: Matrix & Strategy
subtopic: github
group: Jobs & Steps
order: 3
render_with_liquid: false
---

#### Matrix build

{% raw %}
```yaml
jobs:
  test:
    strategy:
      fail-fast: false
      matrix:
        node: [18, 20, 22]
        os: [ubuntu-latest, windows-latest]
    runs-on: ${{ matrix.os }}
    steps:
      - uses: actions/setup-node@v4
        with:
          node-version: ${{ matrix.node }}
      - run: npm test
```
{% endraw %}

#### Exclude & include

```yaml
matrix:
  node: [18, 20]
  os: [ubuntu-latest, windows-latest]
  exclude:
    - os: windows-latest
      node: 18
  include:
    - os: ubuntu-latest
      node: 22
      experimental: true
```
