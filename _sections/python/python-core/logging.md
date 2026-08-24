---
title: Logging
subtopic: python-core
group: Files & System
order: 4
---

#### Basic setup

```python
import logging

logging.basicConfig(
    level=logging.INFO,
    format='%(asctime)s %(levelname)s %(name)s: %(message)s',
)
log = logging.getLogger(__name__)

log.debug('...')    log.info('started')
log.warning('...')  log.error('failed')
log.exception('boom')       # error + traceback (inside except)
```

#### Levels & handlers

```python
DEBUG < INFO < WARNING < ERROR < CRITICAL

log.setLevel(logging.DEBUG)
h = logging.FileHandler('app.log')
h.setFormatter(logging.Formatter('%(message)s'))
log.addHandler(h)

log.info('user %s logged in', user_id)   # lazy %-args
```
