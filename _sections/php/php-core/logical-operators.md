---
title: Logical Operators & Truthiness
subtopic: php-core
group: Types & Operators
order: 4
---

#### Falsy values

```
false   null   0   0.0   ""   "0"   []
```
Everything else is truthy — including `"-1"`, `"false"`, non-empty arrays.

#### Logical operators

```php
&&   ||   !           // high precedence — use in expressions
and  or   xor         // low precedence — can surprise in assignments:

$a = true  || false;  // $a = true  ✓
$a = true  or false;  // ($a = true) or false  — $a = true (fine here)
$a = false || true;   // $a = true  ✓
$a = false or true;   // ($a = false) or true  — $a = false! ✗
```

#### Ternary & short forms

```php
$v = $cond ? 'yes' : 'no';   // standard ternary
$v = $x ?: 'default';        // Elvis — $x if truthy, else 'default'
$v = $x ?? 'default';        // null coalescing — $x if not null
```

#### Short-circuit evaluation

```php
// Right side only evaluates if needed:
$user && $user->isAdmin();
$val = $cache->get($k) ?? $this->compute($k);
false && expensiveCall();     // expensiveCall never runs
```
