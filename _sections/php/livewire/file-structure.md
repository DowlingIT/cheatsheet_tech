---
title: File Structure
subtopic: livewire
group: Overview
order: 3
---

#### Layout

```
app/
  Livewire/
    Counter.php               component class
    Posts/
      Index.php               nested component (dot notation: posts.index)
      Show.php

resources/views/
  livewire/
    counter.blade.php         view auto-matched to Counter.php by name
    posts/
      index.blade.php
      show.blade.php
  components/                 anonymous Blade components (not Livewire)
  layouts/
    app.blade.php             page layout wrapping full-page components
```

#### Naming convention

```
App\Livewire\Counter        →  livewire/counter.blade.php
App\Livewire\PostList       →  livewire/post-list.blade.php
App\Livewire\Posts\Index    →  livewire/posts/index.blade.php
```

#### Full-page components

```php
// routes/web.php
Route::get('/counter', Counter::class);

// Counter.php — render returns a layout-wrapped view
public function render(): View {
    return view('livewire.counter')->layout('layouts.app');
}
```
