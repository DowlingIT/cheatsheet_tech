---
title: Template Filters
subtopic: django
group: Templates
order: 3
render_with_liquid: false
---

#### String

```django
{{ value|lower }}           {{ value|upper }}
{{ value|title }}           {{ value|capfirst }}
{{ value|truncatechars:50 }}
{{ value|truncatewords:10 }}
{{ value|wordcount }}
{{ value|ljust:"10" }}      {{ value|rjust:"10" }}
{{ value|center:"15" }}
{{ value|slugify }}
```

#### HTML & dates

```django
{{ content|linebreaks }}     {# \n → <p> and <br> #}
{{ content|linebreaksbr }}   {# \n → <br> only #}
{{ content|striptags }}      {# remove HTML tags #}
{{ value|escape }}           {# HTML-escape (default) #}
{{ value|safe }}             {# mark as safe — trusted only #}

{{ date|date:"D, d M Y" }}   {# Mon, 01 Jan 2024 #}
{{ date|date:"Y-m-d" }}
{{ date|time:"H:i" }}
{{ date|timesince }}         {# "3 days ago" #}
{{ date|timeuntil }}
```

#### Numbers & lists

```django
{{ value|floatformat:2 }}    {# 3.14159 → 3.14 #}
{{ value|filesizeformat }}   {# 1048576 → "1.0 MB" #}

{{ list|join:", " }}
{{ list|first }}             {{ list|last }}
{{ list|length }}            {{ list|length_is:"3" }}
{{ list|slice:":3" }}
{{ list|dictsort:"name" }}
{{ value|default:"n/a" }}
{{ value|default_if_none:"unknown" }}
{{ value|yesno:"yes,no,maybe" }}
```
