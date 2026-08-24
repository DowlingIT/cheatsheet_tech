---
title: Templates
subtopic: django
group: Templates
order: 1
render_with_liquid: false
---

#### Inheritance

```django
{# base.html #}
<!DOCTYPE html><html>
<body>{% block content %}{% endblock %}</body>
</html>

{# child.html #}
{% extends "base.html" %}
{% block content %}
  <h1>{{ post.title }}</h1>
{% endblock %}
```

#### Tags & filters

```django
{% include "partials/card.html" with post=post only %}
{% for post in posts %}{{ forloop.counter }}. {{ post.title }}{% empty %}
  <p>No posts.</p>{% endfor %}
{% if user.is_authenticated %}…{% elif user.is_staff %}…{% else %}…{% endif %}
{% with total=posts.count %}{{ total }}{% endwith %}
{% csrf_token %}

{{ post.title|upper }}
{{ post.created_at|date:"Y-m-d" }}
{{ post.body|truncatewords:30 }}
{{ content|linebreaks }}
{{ value|default:"n/a" }}
{{ post.body|safe }}          {# bypass escaping — trusted content only #}
```
