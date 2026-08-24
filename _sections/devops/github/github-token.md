---
title: GITHUB_TOKEN
subtopic: github
group: Secrets & Variables
order: 2
render_with_liquid: false
---

#### Auto-provided token

{% raw %}
```yaml
steps:
  - uses: actions/checkout@v4
    with:
      token: ${{ secrets.GITHUB_TOKEN }}
```
{% endraw %}

#### Set workflow permissions

```yaml
permissions:
  contents: read
  pull-requests: write
  issues: write
  packages: write
  id-token: write       # for OIDC / cloud auth
```

#### Use in API calls

{% raw %}
```yaml
- run: |
    curl -H "Authorization: Bearer ${{ secrets.GITHUB_TOKEN }}" \
      https://api.github.com/repos/${{ github.repository }}/releases
```
{% endraw %}
