---
title: Array Iteration & Unpacking
subtopic: php-core
group: Arrays
order: 3
---

#### Iteration

```php
foreach ($arr as $val) { }
foreach ($arr as $key => $val) { }

array_walk($arr, function(&$val, $key) { $val *= 2; });
```

#### Unpacking (8.1 string keys)

```php
[$first, $second]    = $arr;
[, $second]          = $arr;         // skip index 0
['id' => $id, 'name' => $name] = $row;

// Spread into array
$merged = [...$a, ...$b, 'extra' => true];
```

#### Useful shorthands

```php
compact('id', 'name')          // → ['id' => $id, 'name' => $name]
extract($assoc)                // → creates $key variables (use sparingly)
range(1, 10)                   // [1, 2, ..., 10]
array_fill(0, 5, null)         // 5 nulls
array_pad($arr, 10, 0)
```
