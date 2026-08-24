---
title: Helpers & Collections
subtopic: laravel
group: Helpers & Events
order: 1
---

#### String helpers (Str::)

```php
Str::slug('Hello World')        // 'hello-world'
Str::camel('foo_bar')           // 'fooBar'
Str::snake('FooBar')            // 'foo_bar'
Str::studly('foo_bar')          // 'FooBar'
Str::limit($s, 100, '...')
Str::contains($s, 'needle')     // also accepts array
Str::random(32)
Str::uuid()
```

#### Array helpers (Arr::)

```php
Arr::get($array, 'user.name', 'default')
Arr::set($array, 'user.name', 'Alice')
Arr::pluck($rows, 'name', 'id')
Arr::first($array, fn($v) => $v > 0)
Arr::flatten($array)
```

#### Collection pipeline

```php
collect([1, 2, 3, 4, 5])
    ->filter(fn($n) => $n % 2 === 0)
    ->map(fn($n) => $n * 10)
    ->values()    // re-index
    ->all();      // [20, 40]
```
