---
title: Generators
subtopic: php-core
group: Functions
order: 3
---

#### Generator function

```php
function fibonacci(): Generator {
    [$a, $b] = [0, 1];
    while (true) {
        yield $a;
        [$a, $b] = [$b, $a + $b];
    }
}

$gen = fibonacci();
$gen->current();   // 0
$gen->next();
$gen->current();   // 1
```

#### yield key => value

```php
function indexedWords(string $text): Generator {
    foreach (explode(' ', $text) as $i => $word) {
        yield $i => $word;
    }
}
```

#### yield from (delegation)

```php
function inner(): Generator { yield 1; yield 2; }
function outer(): Generator { yield 0; yield from inner(); yield 3; }
// produces: 0, 1, 2, 3
```
