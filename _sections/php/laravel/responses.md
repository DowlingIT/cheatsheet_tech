---
title: Responses
subtopic: laravel
group: Controllers
order: 3
---

#### Views & JSON

```php
return view('posts.index', compact('posts'));
return response()->json(['id' => $post->id], 201);
return response()->json($data)->withHeaders(['X-Custom' => 'val']);
```

#### File responses

```php
return response()->download(storage_path('exports/file.csv'));
return response()->file(public_path('logo.png'));
return Storage::download('reports/q1.pdf', 'Q1 Report.pdf');
```

#### Abort helpers

```php
abort(404);
abort(403, 'Forbidden');
abort_if(!$post, 404);
abort_unless($user->isAdmin(), 403);
```

#### Flash & session

```php
session()->flash('success', 'Saved!');
session()->put('key', 'value');
session()->get('key', 'default');
session()->forget('key');
session()->flush();
```
