---
title: Secrets & Variables
subtopic: github
group: Secrets & Variables
order: 1
render_with_liquid: false
---

#### Accessing secrets

{% raw %}
```yaml
env:
  API_TOKEN: ${{ secrets.API_TOKEN }}

steps:
  - run: curl -H "Authorization: Bearer $API_TOKEN" $URL
```
{% endraw %}

#### Non-secret variables (vars context)

{% raw %}
```yaml
env:
  APP_URL: ${{ vars.APP_URL }}
  LOG_LEVEL: ${{ vars.LOG_LEVEL }}
```
{% endraw %}

#### Setting env for subsequent steps

```yaml
- run: echo "VERSION=$(npm pkg get version --json | tr -d '"')" >> $GITHUB_ENV
- run: echo "Deploying version $VERSION"
```
