---
title: Resources
subtopic: filament
group: Resources & Navigation
order: 1
---

#### Generate

```bash
php artisan make:filament-resource Post --generate   # auto-generates fields
php artisan make:filament-resource Post --simple      # modal CRUD (no separate pages)
```

#### Resource class

```php
class PostResource extends Resource {
    protected static ?string $model          = Post::class;
    protected static ?string $navigationIcon = 'heroicon-o-document-text';
    protected static ?string $navigationGroup = 'Content';
    protected static ?int    $navigationSort = 1;
    protected static ?string $recordTitleAttribute = 'title';

    public static function form(Form $form): Form { ... }
    public static function table(Table $table): Table { ... }

    public static function getPages(): array {
        return [
            'index'  => Pages\ListPosts::route('/'),
            'create' => Pages\CreatePost::route('/create'),
            'edit'   => Pages\EditPost::route('/{record}/edit'),
        ];
    }
}
```
