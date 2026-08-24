---
title: wire:model Bindings
subtopic: livewire
group: Components
order: 3
render_with_liquid: false
---

#### Binding modes

```blade
<input wire:model="search">          {{-- updates on change --}}
<input wire:model.live="search">     {{-- updates on every keystroke --}}
<input wire:model.blur="search">     {{-- updates on blur --}}
<input wire:model.lazy="search">     {{-- alias for blur --}}
<input wire:model.debounce.500ms="search">

<select wire:model="status">
    <option value="draft">Draft</option>
    <option value="published">Published</option>
</select>

<input type="checkbox" wire:model="active">
<input type="radio"    wire:model="role" value="admin">
```

#### Nested & collection binding

```blade
{{-- Nested form object --}}
<input wire:model="form.title">
<input wire:model="form.tags.0">

{{-- Show error --}}
@error('form.title') {{ $message }} @enderror
```
