---
title: Variable Scope
subtopic: php-core
group: Scope & Namespaces
order: 1
---

#### Function scope (isolated by default)

```php
$msg = 'hello';

function test(): void {
    echo isset($msg) ? 'yes' : 'no';  // 'no' — not visible inside
}
```

#### global keyword

```php
$counter = 0;

function increment(): void {
    global $counter;   // pulls the global into local scope
    $counter++;
}

// Alternative: $GLOBALS['counter']++; (avoid)
```

#### Static local variables

```php
function counter(): int {
    static $n = 0;   // initialized once; survives between calls
    return ++$n;
}
counter(); // 1
counter(); // 2
counter(); // 3
```

#### Closures must capture explicitly

```php
$factor = 5;
$fn = function($x) use ($factor) { return $x * $factor; };
$fn = function($x) use (&$factor) { return $x * $factor; }; // by reference
```
