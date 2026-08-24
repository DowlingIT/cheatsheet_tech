---
title: Component Class
subtopic: livewire
group: Components
order: 1
---

#### Generate & register

```bash
php artisan make:livewire PostList
# → app/Livewire/PostList.php
# → resources/views/livewire/post-list.blade.php
```

#### Component class

```php
namespace App\Livewire;

use Livewire\Component;

class PostList extends Component {
    public string $search = '';
    public int $perPage = 10;

    public function render(): View {
        return view('livewire.post-list', [
            'posts' => Post::where('title', 'like', "%{$this->search}%")
                          ->paginate($this->perPage),
        ]);
    }
}
```

#### Use in Blade / pass props

```blade
<livewire:post-list />
<livewire:post-list :per-page="20" />
@livewireScripts
```
