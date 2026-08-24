---
title: Dates & Times
subtopic: python-core
group: Strings, Dates & Encoding
order: 3
---

#### datetime & timedelta

```python
from datetime import datetime, date, timedelta

now = datetime.now()          today = date.today()
dt = datetime(2026, 7, 28, 14, 30)
dt + timedelta(days=7, hours=3)
delta = dt2 - dt1             # a timedelta
delta.days   delta.total_seconds()
```

#### Format, parse, timezones

```python
dt.strftime('%Y-%m-%d %H:%M')    # → '2026-07-28 14:30'
datetime.strptime('2026-07-28', '%Y-%m-%d')
dt.isoformat()      datetime.fromisoformat(s)

from zoneinfo import ZoneInfo
datetime.now(ZoneInfo('America/New_York'))
dt.astimezone(ZoneInfo('UTC'))   # convert tz

import locale                    # locale-aware formatting
locale.setlocale(locale.LC_ALL, 'en_US.UTF-8')
```
