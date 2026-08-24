---
title: Lifecycle Hooks
subtopic: livewire
group: Components
order: 2
---

#### Hooks

```php
public function mount(int $postId): void {
    // First request only — runs like a constructor
    $this->post = Post::findOrFail($postId);
}

public function hydrate(): void { }    // start of every subsequent request
public function dehydrate(): void { }  // end of every response

// Before any property update
public function updating(string $name, mixed $value): void { }

// After specific property changes (camelCase property name)
public function updatedSearch(): void {
    $this->resetPage();
}

// After nested property (form.email → updatedFormEmail)
public function updatedFormEmail(string $value): void {
    $this->validateOnly('form.email');
}
```
