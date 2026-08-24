---
title: Actions
subtopic: livewire
group: Actions & Events
order: 1
render_with_liquid: false
---

#### Calling methods from Blade

```blade
<button wire:click="save">Save</button>
<button wire:click="delete({{ $post->id }})">Delete</button>
<input  wire:keydown.enter="search">
<input  wire:keydown.escape="clear">
<form   wire:submit="store">...</form>
<select wire:change="filter($event.target.value)">
```

#### Redirect & flash in method

```php
public function store(): void {
    $this->validate();
    Post::create($this->form->all());
    session()->flash('message', 'Post created!');
    $this->redirect(route('posts.index'), navigate: true);
}
```

#### Magic methods from Blade

```blade
<button wire:click="$set('count', 0)">Reset</button>
<button wire:click="$refresh">Refresh</button>
<button wire:click="$toggle('showModal')">Toggle</button>
<button wire:click="$dispatch('post-saved', { id: 1 })">Dispatch</button>
```
