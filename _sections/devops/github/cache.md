---
title: Caching
subtopic: github
group: Artifacts & Cache
order: 2
render_with_liquid: false
---

#### Manual cache action

{% raw %}
```yaml
- uses: actions/cache@v4
  with:
    path: ~/.npm
    key: ${{ runner.os }}-npm-${{ hashFiles('**/package-lock.json') }}
    restore-keys: |
      ${{ runner.os }}-npm-
```
{% endraw %}

#### Built-in caching via setup actions

```yaml
- uses: actions/setup-node@v4
  with:
    node-version: 20
    cache: npm            # handles cache key automatically

- uses: actions/setup-python@v5
  with:
    python-version: '3.12'
    cache: pip
```
