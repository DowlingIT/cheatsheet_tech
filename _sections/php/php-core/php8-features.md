---
title: PHP 8 Features
subtopic: php-core
group: Language Reference
order: 3
---

#### Named arguments & nullsafe (8.0)

```php
str_pad(string: $s, length: 10, pad_type: STR_PAD_LEFT);

$city = $user?->address?->city;   // returns null if any link is null
```

#### Enums (8.1)

```php
enum Status: string {
    case Active   = 'active';
    case Inactive = 'inactive';
}

Status::from('active');      // Status::Active
Status::tryFrom('x');        // null
Status::Active->value;       // 'active'
Status::cases();             // all cases as array
```

#### Readonly & constructor promotion (8.1 / 8.0)

```php
class Point {
    public function __construct(
        public readonly float $x,
        public readonly float $y,
    ) {}
}
```

#### Fibers (8.1)

```php
$fiber = new Fiber(fn() => Fiber::suspend('hello'));
$val = $fiber->start(); // 'hello'
```
