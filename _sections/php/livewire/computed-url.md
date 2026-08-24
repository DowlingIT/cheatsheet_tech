---
title: Computed Properties & URL
subtopic: livewire
group: Data & Validation
order: 1
render_with_liquid: false
---

#### Computed properties

```php
use Livewire\Attributes\Computed;

#[Computed]
public function posts(): Collection {
    return Post::where('status', 'published')->get();
}

// In template: {{ $this->posts->count() }}
// Cached per request; bust with: unset($this->posts);
```

#### URL query sync

```php
use Livewire\Attributes\Url;

#[Url]
public string $search = '';          // synced to ?search=

#[Url(as: 'q', keep: true)]
public string $query = '';           // synced to ?q=, kept on nav

// Use with pagination to persist page in URL
#[Url]
public int $page = 1;
```

#### Locked & session

```php
use Livewire\Attributes\{Locked, Session};

#[Locked]
public int $userId;     // cannot be set from client-side

#[Session]
public array $filters = [];  // persisted in PHP session
```
