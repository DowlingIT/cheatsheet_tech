---
title: Date & Time
subtopic: php-core
group: File & DateTime
order: 3
---

#### Timestamps & date()

```php
time()                          // Unix timestamp (int)
microtime(true)                 // float with microseconds
date('Y-m-d H:i:s')            // '2026-07-03 14:30:00'
date('D, d M Y', $ts)          // 'Thu, 03 Jul 2026'
date('U')                       // same as time()
strtotime('next Monday')        // timestamp
strtotime('+7 days', $ts)
mktime(14, 30, 0, 7, 3, 2026)  // hour, min, sec, month, day, year
```

#### DateTime class

```php
$dt = new \DateTime('now');
$dt = new \DateTime('2026-01-01', new \DateTimeZone('UTC'));
$dt->format('Y-m-d H:i:s');
$dt->modify('+1 month');
$dt->add(new \DateInterval('P1Y2M3DT4H')); // ISO 8601 duration

$diff = $start->diff($end);   // DateInterval
$diff->days;   $diff->h;   $diff->i;   $diff->s;
```

#### Immutable (prefer this)

```php
$dt  = new \DateTimeImmutable('now');
$dt2 = $dt->modify('+1 day');  // $dt unchanged; $dt2 is new instance
```
