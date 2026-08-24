---
title: Types
subtopic: php-core
group: Types & Operators
order: 1
---

#### Scalar & compound

```
int    float    string    bool
array  object   callable  iterable
```

#### Special (PHP 8)

```
null   void   never   mixed
```

#### Union, intersection & nullable

```php
function id(int|string $v): int|string {}
function log(Countable&Iterator $v): void {}  // 8.1 intersection
function find(int $id): ?User {}              // nullable
```

#### Type juggling & casting

```php
(int)'42'       (float)'3.14'
(string)99      (bool)0       (array)$obj
intval($s)      floatval($s)
settype($var, 'int')
gettype($var)   // 'integer', 'string', etc.
is_int($v)  is_string($v)  is_array($v)  is_null($v)
```
