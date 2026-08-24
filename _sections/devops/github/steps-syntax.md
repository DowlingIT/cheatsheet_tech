---
title: Steps
subtopic: github
group: Jobs & Steps
order: 2
render_with_liquid: false
---

#### Action vs command

```yaml
steps:
  - name: Checkout
    uses: actions/checkout@v4

  - name: Install
    run: npm ci

  - name: Multi-line run
    run: |
      echo "Building..."
      npm run build
```

#### Step options

{% raw %}
```yaml
- name: Deploy
  uses: ./local-action
  with:
    token: ${{ secrets.TOKEN }}
  env:
    NODE_ENV: production
  if: success()
  continue-on-error: true
  id: deploy_step
```
{% endraw %}

#### Capture step output

{% raw %}
```yaml
- id: vars
  run: echo "sha=$(git rev-parse --short HEAD)" >> $GITHUB_OUTPUT

- run: echo "SHA is ${{ steps.vars.outputs.sha }}"
```
{% endraw %}
