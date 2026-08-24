---
title: Constructor Promotion & Traits
subtopic: php-core
group: Classes & OOP
order: 2
---

#### Constructor promotion (8.0)

```php
class Point {
    public function __construct(
        public readonly float $x,
        public readonly float $y,
        protected string $label = '',
    ) {}
}

new Point(x: 1.0, y: 2.5);
```

#### Traits

```php
trait HasTimestamps {
    public \DateTime $createdAt;
    public \DateTime $updatedAt;

    public function touch(): void {
        $this->updatedAt = new \DateTime;
    }
}

class Post {
    use HasTimestamps;
    use SoftDeletes { delete as softDelete; }  // alias
}
```

#### Late static binding

```php
class Base {
    public static function create(): static { return new static; }
}
class Child extends Base {} // Child::create() returns Child
```
