---
title: Variables & Context
subtopic: django
group: Templates
order: 2
render_with_liquid: false
---

#### Variable lookup

```django
{{ post.title }}           {# attribute #}
{{ post.author.username }} {# chained lookup #}
{{ request.user.email }}   {# request context processor needed #}
{{ my_dict.key }}          {# dict key #}
{{ my_list.0 }}            {# list index #}
{{ post.get_status_display }} {# choices display value #}
```

#### forloop variables

```django
{% for post in posts %}
  {{ forloop.counter }}    {# 1-indexed #}
  {{ forloop.counter0 }}   {# 0-indexed #}
  {{ forloop.revcounter }} {# countdown #}
  {{ forloop.first }}      {# True on first iteration #}
  {{ forloop.last }}       {# True on last iteration #}
  {{ forloop.parentloop }} {# outer loop in nested loops #}
{% endfor %}
```

#### Useful context variables

```django
{{ request.method }}       {# GET, POST #}
{{ request.path }}         {# /blog/posts/ #}
{{ request.GET.q }}        {# query param #}
{{ request.session.key }}
{{ messages }}             {# django.contrib.messages #}
```
