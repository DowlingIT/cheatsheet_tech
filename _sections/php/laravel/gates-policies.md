---
title: Gates & Policies
subtopic: laravel
group: Middleware & Auth
order: 3
---

#### Gates

```php
// Define (AppServiceProvider::boot)
Gate::define('update-post', function (User $user, Post $post): bool {
    return $user->id === $post->user_id;
});

// Check
Gate::allows('update-post', $post)    // bool
Gate::denies('update-post', $post)
Gate::authorize('update-post', $post) // throws 403
$request->user()->can('update-post', $post)
```

#### Policies

```php
// app/Policies/PostPolicy.php (auto-discovered)
class PostPolicy {
    public function update(User $user, Post $post): bool {
        return $user->id === $post->user_id;
    }
    public function delete(User $user, Post $post): bool {
        return $user->isAdmin() || $user->id === $post->user_id;
    }
}

// In controller
$this->authorize('update', $post);

// In Blade
@can('update', $post) <a href="…">Edit</a> @endcan
```
