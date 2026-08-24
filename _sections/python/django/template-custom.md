---
title: Custom Template Tags & Filters
subtopic: django
group: Templates
order: 4
render_with_liquid: false
---

#### Setup

```
myapp/
  templatetags/
    __init__.py
    myapp_tags.py
```

#### Tags

```python
# myapp/templatetags/myapp_tags.py
from django import template

register = template.Library()

@register.simple_tag
def current_year():
    return datetime.now().year

@register.simple_tag(takes_context=True)
def active_nav(context, url_name):
    return 'active' if context['request'].resolver_match.url_name == url_name else ''

@register.inclusion_tag('partials/recent_posts.html')
def recent_posts(count=5):
    return {'posts': Post.objects.published()[:count]}
```

#### Filters

```python
@register.filter
def reading_time(text):
    words = len(text.split())
    return max(1, words // 200)  # minutes

@register.filter(name='currency')
def currency_format(value, symbol='$'):
    return f'{symbol}{value:,.2f}'
```

#### Usage in templates

```django
{% load myapp_tags %}
{% current_year %}
<span class="{% active_nav 'home' %}">Home</span>
{% recent_posts count=3 %}
{{ post.body|reading_time }} min read
```
