---
title: Operators
subtopic: php-core
group: Types & Operators
order: 3
---

#### PHP-specific

```php
$s = 'Hello' . ' World';   // string concat
$s .= '!';                 // concat-assign

$cmp = $a <=> $b;          // spaceship: -1 / 0 / 1
$r = @file_get_contents($p); // @ silences errors (avoid)
```

#### Comparison

```php
==   // loose equality  (1 == '1' → true)
===  // strict equality (1 === '1' → false)
!=   // loose not-equal
!==  // strict not-equal
```

#### Spread & destructuring

```php
function sum(int ...$nums): int { return array_sum($nums); }
sum(...[1, 2, 3]);               // spread into call

$merged = [...$a, ...$b];        // spread into array

[$first, $second] = $arr;
[, $second]       = $arr;        // skip first
['id' => $id]     = $assoc;
```
