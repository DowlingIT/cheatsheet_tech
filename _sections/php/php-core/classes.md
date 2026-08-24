---
title: Class Structure
subtopic: php-core
group: Classes & OOP
order: 1
---

#### Class anatomy

```php
class Animal {
    public string $name;
    protected int $age  = 0;
    private static int $count = 0;

    public function __construct(string $name) {
        $this->name = $name;
        self::$count++;
    }

    public static function count(): int { return self::$count; }
}

class Dog extends Animal implements Runnable {
    use HasTimestamps;

    public function run(): void {}
}
```

#### Abstract & interface

```php
abstract class Base {
    abstract public function handle(): void;
    public function run(): void { $this->handle(); }
}

interface Serializable {
    public function serialize(): string;
    public function unserialize(string $data): void;
}
```
