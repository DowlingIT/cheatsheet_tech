---
title: Seeders & Factories
subtopic: laravel
group: Migrations
order: 3
---

#### Factory definition

```php
class PostFactory extends Factory {
    public function definition(): array {
        return [
            'user_id' => User::factory(),
            'title'   => fake()->sentence(),
            'slug'    => fake()->unique()->slug(),
            'body'    => fake()->paragraphs(3, true),
            'status'  => fake()->randomElement(['draft', 'published']),
        ];
    }

    public function published(): static {
        return $this->state(['status' => 'published', 'published_at' => now()]);
    }
}
```

#### Using factories & seeders

```php
Post::factory()->count(10)->create();
Post::factory()->published()->create(['title' => 'Pinned']);
Post::factory()->for(User::find(1))->count(5)->create();

class PostSeeder extends Seeder {
    public function run(): void { Post::factory(50)->create(); }
}
// php artisan db:seed --class=PostSeeder
```
