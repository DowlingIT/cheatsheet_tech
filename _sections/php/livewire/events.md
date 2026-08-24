---
title: Events
subtopic: livewire
group: Actions & Events
order: 2
render_with_liquid: false
---

#### Dispatch

```php
// From component PHP
$this->dispatch('post-saved', id: $post->id);
$this->dispatch('notify')->to(NotificationBell::class);
$this->dispatch('refresh')->self();
```

#### Listen with attribute

```php
use Livewire\Attributes\On;

#[On('post-saved')]
public function onPostSaved(int $id): void {
    $this->posts = Post::all();
}
```

#### Browser events

```blade
{{-- Trigger JS custom event --}}
<button wire:click="$dispatchTo('notifications', 'refresh')">

{{-- Listen from Alpine --}}
<div x-on:post-saved.window="showToast($event.detail.id)">
```
