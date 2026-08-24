---
title: Column Types
subtopic: laravel
group: Migrations
order: 2
---

#### Common types

```php
$table->id()                        // bigIncrements PK
$table->string('name', 100)
$table->text('body')                // also longText() tinyText()
$table->integer('age')              // bigInteger() unsignedBigInteger()
$table->decimal('price', 8, 2)
$table->boolean('active')
$table->json('settings')
$table->date('dob')
$table->dateTime('scheduled_at')    // also timestamp()
$table->enum('role', ['admin', 'user'])
$table->uuid()
$table->foreignId('user_id')->constrained()
```

#### Modifiers

```php
->nullable()
->default('value')
->unique()          ->index()
->after('column')   ->first()
->comment('note')
->unsigned()
->cascadeOnDelete()  ->nullOnDelete()
```
