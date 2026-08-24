---
title: Common Actions
subtopic: github
group: Jobs & Steps
order: 1
render_with_liquid: false
---

#### Checkout & runtimes

```yaml
- uses: actions/checkout@v4
  with:
    fetch-depth: 0          # full history; default is 1

- uses: actions/setup-node@v4
  with:
    node-version: '20'
    cache: npm

- uses: actions/setup-python@v5
  with:
    python-version: '3.12'
    cache: pip

- uses: actions/setup-java@v4
  with:
    distribution: temurin
    java-version: '21'
```

#### Container registry

{% raw %}
```yaml
- uses: docker/login-action@v3
  with:
    registry: ghcr.io
    username: ${{ github.actor }}
    password: ${{ secrets.GITHUB_TOKEN }}

- uses: docker/build-push-action@v6
  with:
    push: true
    tags: ghcr.io/${{ github.repository }}:latest
```
{% endraw %}
