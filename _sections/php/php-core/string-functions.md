---
title: String Functions
subtopic: php-core
group: Strings
order: 2
---

#### Search & test (8.0+)

```php
str_contains($s, 'foo')
str_starts_with($s, 'foo')
str_ends_with($s, 'foo')
strpos($s, 'foo')          // int|false
substr_count($s, 'foo')
strlen($s)
```

#### Transform

```php
strtolower($s)  strtoupper($s)  ucfirst($s)  ucwords($s)
trim($s)        ltrim($s)       rtrim($s)
str_replace('a', 'b', $s)
str_pad($s, 10, ' ', STR_PAD_LEFT)
str_repeat('ab', 3)          // 'ababab'
substr($s, 2, 5)
sprintf('%05d', 42)          // '00042'
number_format(1234.5, 2)     // '1,234.50'
```
