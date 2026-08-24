---
title: Form Objects
subtopic: livewire
group: Data & Validation
order: 3
render_with_liquid: false
---

#### Form class (Livewire 3)

```php
use Livewire\Form;

class PostForm extends Form {
    #[Validate('required|min:3|max:255')]
    public string $title = '';

    #[Validate('required')]
    public string $body = '';

    public function fill(Post $post): void {
        $this->title = $post->title;
        $this->body  = $post->body;
    }

    public function store(): Post {
        return Post::create($this->all());
    }
}
```

#### Using the form in a component

```php
class CreatePost extends Component {
    public PostForm $form;

    public function save(): void {
        $this->form->validate();
        $this->form->store();
        $this->redirect('/posts');
    }
}
```

```blade
<input wire:model="form.title">
@error('form.title') {{ $message }} @enderror
```
