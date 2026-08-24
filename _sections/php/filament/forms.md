---
title: Form Fields
subtopic: filament
group: Forms
order: 1
---

#### Common fields

```php
use Filament\Forms\Components\{TextInput, Textarea, Select,
    Toggle, DatePicker, FileUpload, RichEditor, MarkdownEditor};

TextInput::make('title')->required()->maxLength(255)->columnSpanFull(),

Select::make('status')
    ->options(['draft' => 'Draft', 'published' => 'Published'])
    ->default('draft')->required(),

Select::make('user_id')
    ->relationship('user', 'name')
    ->searchable()->preload()->required(),

RichEditor::make('body')->required()->columnSpanFull(),
MarkdownEditor::make('body'),
FileUpload::make('image')->image()->directory('posts'),
Toggle::make('featured')->inline(false),
DatePicker::make('published_at')->nullable(),
```
