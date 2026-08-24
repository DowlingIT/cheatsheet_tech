---
title: Form Requests & Validation
subtopic: laravel
group: Controllers
order: 2
---

#### Form request class

```php
class StorePostRequest extends FormRequest {
    public function authorize(): bool {
        return $this->user()->can('create', Post::class);
    }

    public function rules(): array {
        return [
            'title'  => ['required', 'string', 'max:255'],
            'body'   => ['required', 'string'],
            'tags'   => ['array', 'max:5'],
            'tags.*' => ['string', 'max:50'],
            'status' => ['required', Rule::in(['draft', 'published'])],
            'email'  => ['required', 'email', Rule::unique('users')->ignore($this->user)],
        ];
    }
}
```

#### Inline validation

```php
$validated = $request->validate([
    'email' => 'required|email|unique:users',
    'age'   => 'required|integer|min:18',
]);

Validator::make($data, $rules)->validate();  // throws on fail
```
