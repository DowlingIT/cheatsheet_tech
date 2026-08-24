---
title: Caching
subtopic: django
group: Caching & Email
order: 1
---

#### settings.py backends

```python
# Redis (recommended)
CACHES = {
    'default': {
        'BACKEND': 'django.core.cache.backends.redis.RedisCache',
        'LOCATION': 'redis://127.0.0.1:6379/1',
    }
}

# Memcached
CACHES = {'default': {
    'BACKEND': 'django.core.cache.backends.memcached.PyMemcacheCache',
    'LOCATION': '127.0.0.1:11211',
}}

# Local memory (dev / single process)
CACHES = {'default': {'BACKEND': 'django.core.cache.backends.locmem.LocMemCache'}}
```

#### View caching

```python
from django.views.decorators.cache import cache_page, never_cache
from django.utils.decorators import method_decorator

@cache_page(60 * 15)    # 15 minutes
def post_list(request): ...

@method_decorator(cache_page(60 * 60), name='dispatch')
class PostListView(ListView): ...
```

#### Low-level cache API

```python
from django.core.cache import cache

cache.set('key', value, timeout=300)
cache.get('key', default=None)
cache.get_or_set('key', lambda: compute(), timeout=300)
cache.delete('key')
cache.clear()

# Multiple keys
cache.set_many({'a': 1, 'b': 2}, timeout=300)
cache.get_many(['a', 'b'])
```
