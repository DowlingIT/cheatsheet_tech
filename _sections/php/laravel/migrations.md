---
title: Migrations
subtopic: laravel
group: Migrations
order: 1
---

#### Migration structure

```php
public function up(): void {
    Schema::create('posts', function (Blueprint $table) {
        $table->id();
        $table->foreignId('user_id')->constrained()->cascadeOnDelete();
        $table->string('title');
        $table->string('slug')->unique();
        $table->text('body');
        $table->enum('status', ['draft', 'published'])->default('draft');
        $table->timestamp('published_at')->nullable();
        $table->timestamps();
        $table->softDeletes();
    });
}

public function down(): void {
    Schema::dropIfExists('posts');
}
```

#### Alter existing table

```php
Schema::table('posts', function (Blueprint $table) {
    $table->string('excerpt', 500)->nullable()->after('body');
    $table->dropColumn('old_column');
    $table->renameColumn('slug', 'url_slug');
    $table->index(['status', 'published_at']);
});
```
