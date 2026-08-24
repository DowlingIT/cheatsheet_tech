---
title: Closures & Arrows
subtopic: php-core
group: Functions
order: 2
---

#### Closure with use

```php
$multiplier = 3;
$fn = function(int $n) use ($multiplier): int {
    return $n * $multiplier;
};
// use (&$var) to capture by reference
```

#### Arrow functions (7.4+)

```php
$double = fn($n) => $n * 2;    // auto-captures outer scope

$prices = array_map(
    fn($item) => $item->price * 1.2,
    $items
);
```

#### Static closure

```php
$fn = static function($x) { return $x; }; // no $this binding
```

#### Binding

```php
$fn = Closure::bind($closure, $newThis, $newScope);
$fn = $closure->bindTo($obj);
```
