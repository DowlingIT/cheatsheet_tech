---
title: Array Functions
subtopic: php-core
group: Arrays
order: 2
---

#### Transform

```php
array_map(fn($x) => $x * 2, $arr)
array_filter($arr, fn($x) => $x > 0)  // reindexes needed after
array_values(array_filter($arr, $fn))  // re-index
array_reduce($arr, fn($carry, $x) => $carry + $x, 0)
```

#### Search

```php
in_array($val, $arr)
in_array($val, $arr, strict: true)
array_search($val, $arr)          // key or false
array_key_exists('k', $arr)
```

#### Combine & split

```php
array_merge($a, $b)           // reindexes int keys
array_unique($arr)
array_flip($arr)              // swap keys ↔ values
array_combine($keys, $vals)
array_chunk($arr, 3)          // split into chunks
array_slice($arr, 2, 5)
array_diff($a, $b)
array_intersect($a, $b)
array_column($rows, 'name')   // pluck a column
```
