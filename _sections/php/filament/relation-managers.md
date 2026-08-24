---
title: Relation Managers
subtopic: filament
group: Resources & Navigation
order: 3
---

#### Generate

```bash
php artisan make:filament-relation-manager PostResource comments body
```

#### Relation manager class

```php
class CommentsRelationManager extends RelationManager {
    protected static string $relationship = 'comments';

    public function form(Form $form): Form {
        return $form->schema([
            Forms\Components\Textarea::make('body')->required(),
        ]);
    }

    public function table(Table $table): Table {
        return $table
            ->columns([
                Tables\Columns\TextColumn::make('body')->limit(50),
                Tables\Columns\TextColumn::make('user.name'),
            ])
            ->headerActions([Tables\Actions\CreateAction::make()])
            ->actions([Tables\Actions\EditAction::make(), Tables\Actions\DeleteAction::make()])
            ->bulkActions([Tables\Actions\BulkActionGroup::make([
                Tables\Actions\DeleteBulkAction::make(),
            ])]);
    }
}
```

```php
// Register in PostResource
public static function getRelations(): array {
    return [CommentsRelationManager::class];
}
```
