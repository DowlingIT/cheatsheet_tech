---
title: Contexts & Expressions
subtopic: github
group: Secrets & Variables
order: 3
render_with_liquid: false
---

#### Common context values

{% raw %}
```yaml
${{ github.sha }}           # full commit SHA
${{ github.ref_name }}      # branch or tag name
${{ github.actor }}         # user who triggered the run
${{ github.repository }}    # owner/repo
${{ github.event_name }}    # push, pull_request, etc.
${{ runner.os }}            # Linux, Windows, macOS
${{ env.MY_VAR }}           # env variable
${{ job.status }}           # success, failure, cancelled
```
{% endraw %}

#### Conditional expressions

```yaml
if: github.event_name == 'push'
if: contains(github.ref, 'main')
if: startsWith(github.ref, 'refs/tags/')
if: failure()
if: always()
if: cancelled()
```
