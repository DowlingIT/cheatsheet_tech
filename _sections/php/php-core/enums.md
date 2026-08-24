---
title: Enums (8.1)
subtopic: php-core
group: Classes & OOP
order: 4
---

#### Pure enum

```php
enum Direction { case North; case South; case East; case West; }

$d = Direction::North;
$d instanceof Direction;    // true
```

#### Backed enum (int or string)

```php
enum Color: string {
    case Red   = 'red';
    case Green = 'green';
    case Blue  = 'blue';

    public function label(): string {
        return ucfirst($this->value);
    }
}

Color::from('red');         // Color::Red  — throws on unknown
Color::tryFrom('purple');   // null
Color::Red->value;          // 'red'
Color::Red->name;           // 'Red'
Color::cases();             // [Color::Red, Color::Green, Color::Blue]
```

#### Enum interfaces & constants

```php
enum Status: int implements HasLabel {
    case Active   = 1;
    case Inactive = 0;

    const DEFAULT = self::Active;
}
```
