---
title: Controllers
subtopic: laravel
group: Controllers
order: 1
---

#### Resource controller

```php
class PostController extends Controller {
    public function index(): View {
        return view('posts.index', ['posts' => Post::paginate(15)]);
    }

    public function store(StorePostRequest $request): RedirectResponse {
        Post::create($request->validated());
        return redirect()->route('posts.index')->with('success', 'Created');
    }

    public function show(Post $post): View {       // route-model binding
        return view('posts.show', compact('post'));
    }

    public function update(UpdatePostRequest $request, Post $post): RedirectResponse {
        $post->update($request->validated());
        return back()->with('success', 'Updated');
    }

    public function destroy(Post $post): RedirectResponse {
        $post->delete();
        return redirect()->route('posts.index');
    }
}
```
