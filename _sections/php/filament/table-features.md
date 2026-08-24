---
title: Filters & Actions
subtopic: filament
group: Tables
order: 2
---

#### Filters

```php
Tables\Filters\SelectFilter::make('status')
    ->options(['draft' => 'Draft', 'published' => 'Published']),

Tables\Filters\Filter::make('featured')
    ->query(fn(Builder $q) => $q->where('featured', true))
    ->toggle(),

Tables\Filters\TrashedFilter::make(),  // requires SoftDeletes
```

#### Row actions

```php
Tables\Actions\EditAction::make(),
Tables\Actions\DeleteAction::make(),
Tables\Actions\Action::make('publish')
    ->icon('heroicon-o-check-circle')
    ->action(fn(Post $r) => $r->update(['status' => 'published']))
    ->requiresConfirmation()
    ->color('success'),
Tables\Actions\ReplicateAction::make(),
```

#### Bulk actions & header

```php
Tables\Actions\BulkActionGroup::make([
    Tables\Actions\DeleteBulkAction::make(),
    Tables\Actions\BulkAction::make('publish')
        ->action(fn(Collection $r) => $r->each->update(['status' => 'published'])),
]),
Tables\Actions\CreateAction::make(),   // header action
```
