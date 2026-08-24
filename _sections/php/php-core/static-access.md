---
title: Object & Class Access
subtopic: php-core
group: Classes & OOP
order: 5
---

#### Instance access (->)

```php
$obj->property;              // read property
$obj->property = 'value';   // write property
$obj->method();              // call method
$obj->method()->chain();     // chaining

$obj?->property;             // nullsafe — null if $obj is null
$obj?->method()?->nested();  // short-circuits on first null
```

#### Static & class access (::)

```php
Counter::increment();        // static method
Counter::$count;             // static property
Config::VERSION;             // class constant
ClassName::class;            // 'Fully\Qualified\ClassName'

self::method();    // class where method is defined (no late binding)
static::method();  // calling class — late static binding
parent::method();  // parent class
```

#### => in context

```
['key' => 'val']              array key-value pair
foreach ($a as $k => $v)      iteration key + value
match($x) { 1 => 'one' }     match arm
fn($x) => $x * 2             arrow function body
```
