---
title: Array Basics
subtopic: php-core
group: Arrays
order: 1
---

#### Create & access

```php
$a = [1, 2, 3];
$m = ['key' => 'val', 'n' => 42];
$a[] = 4;           // append
$a[0];              // indexed
$m['key'];          // associative
count($a)
```

#### Stack / queue

```php
array_push($a, $v);    array_pop($a);
array_unshift($a, $v); array_shift($a);
```

#### Sort

```php
sort($a);    rsort($a);            // indexed
asort($a);   arsort($a);           // preserve keys
ksort($a);   krsort($a);           // by key
usort($a, fn($x, $y) => $x <=> $y);
uasort($a, $fn);  uksort($a, $fn);
```
