---
title: JS Interop
subtopic: livewire
group: Actions & Events
order: 3
render_with_liquid: false
---

#### Alpine.js via $wire

```blade
<div x-data>
    <span x-text="$wire.count"></span>
    <button x-on:click="$wire.count = 0">Reset</button>
    <button x-on:click="$wire.increment()">+1</button>
    <button x-on:click="await $wire.save()">Save</button>
</div>
```

#### Plain JavaScript

```js
Livewire.on('post-saved', ({ id }) => console.log(id));
Livewire.dispatch('notify', { message: 'Hello' });

// Navigate (SPA-style, requires wire:navigate)
Livewire.navigate('/posts');
```

#### wire:navigate (SPA mode)

```blade
<a href="{{ route('posts.index') }}" wire:navigate>Posts</a>
<a href="…" wire:navigate.hover>Prefetch on hover</a>
```
