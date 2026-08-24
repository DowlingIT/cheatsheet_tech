---
title: Variables & Constants
subtopic: php-core
group: Types & Operators
order: 2
---

#### Declaration & reference

```php
$name = 'Alice';
$ref  = &$name;    // reference — changes both
$$key = 'hello';   // variable variable: $$key sets $hello
```

#### Constants

```php
const MAX_RETRIES = 3;
define('VERSION', '1.0');

PHP_EOL           PHP_INT_MAX       PHP_INT_MIN
PHP_FLOAT_EPSILON PHP_MAJOR_VERSION PHP_OS
```

#### Null handling

```php
$val = $a ?? $b ?? 'default';   // null coalescing
$a ??= 'default';               // null coalescing assignment
isset($var)   // true if set and not null
empty($var)   // true if falsy (0, '', [], null, false)
unset($var)
```
