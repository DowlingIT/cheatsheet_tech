---
title: Artisan Commands
subtopic: livewire
group: Overview
order: 2
---

#### Generate components

```bash
php artisan make:livewire Counter             # app/Livewire/Counter.php
                                              # resources/views/livewire/counter.blade.php

php artisan make:livewire posts.Index         # nested — dot = directory separator
                                              # App\Livewire\Posts\Index
                                              # livewire/posts/index.blade.php

php artisan make:livewire --test Counter      # also generates a Pest/PHPUnit test
php artisan make:livewire --inline Counter    # template inlined in the class (no blade file)
```

#### Volt (single-file components)

```bash
php artisan make:volt counter                 # resources/views/livewire/counter.blade.php
                                              # contains both PHP and Blade in one file
php artisan make:volt posts/index --class     # class-based Volt syntax
```

#### Config & assets

```bash
php artisan livewire:publish --config         # publish config/livewire.php
php artisan livewire:publish --assets         # publish JS assets to public/vendor/livewire
php artisan livewire:upgrade                  # upgrade assistant (v2 → v3)
```

#### Testing

```bash
php artisan make:test --unit CounterTest
# In test: Livewire::test(Counter::class)->set('count', 5)->call('increment')->assertSet('count', 6)
```
