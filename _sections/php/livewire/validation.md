---
title: Validation
subtopic: livewire
group: Data & Validation
order: 2
render_with_liquid: false
---

#### Attribute-based rules

```php
use Livewire\Attributes\Validate;

#[Validate('required|min:3|max:255')]
public string $title = '';

#[Validate(['required', 'email', 'unique:users'])]
public string $email = '';
```

#### Inline validate()

```php
public function save(): void {
    $this->validate([
        'title' => 'required|min:3',
        'email' => 'required|email',
    ]);
    User::create(['title' => $this->title]);
}

// Real-time: validate one field
public function updatedEmail(): void {
    $this->validateOnly('email');
}
```

#### Displaying errors in Blade

```blade
@error('title') <span class="error">{{ $message }}</span> @enderror
@error('form.email') {{ $message }} @enderror

{{-- Reset errors --}}
{{-- $this->resetValidation() or $this->resetValidation('email') --}}
```
