---
title: Functions
subtopic: php-core
group: Functions
order: 1
---

#### Typed parameters & defaults

```php
function add(int $a, int $b = 0): int {
    return $a + $b;
}

function log(string ...$msgs): void {
    foreach ($msgs as $m) echo $m . PHP_EOL;
}
```

#### Named arguments (8.0)

```php
function create(string $name, int $age = 0, bool $active = true): User {}

create(name: 'Alice', active: false);   // skip $age
htmlspecialchars(string: $s, flags: ENT_QUOTES);
```

#### First-class callables (8.1)

```php
$fn = strlen(...);               // Closure from built-in
$fn = $obj->method(...);
array_map(strtoupper(...), $arr);
```
