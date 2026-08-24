---
title: "make: Commands"
subtopic: laravel
group: Artisan CLI
order: 1
---

#### Models & database

```bash
php artisan make:model Post              # app/Models/Post.php
php artisan make:model Post -m           # + database migration
php artisan make:model Post -mf          # + migration + factory
php artisan make:model Post -mfcr        # + migration + factory + resource controller
php artisan make:model Post --all        # everything: model, migration, factory,
                                         #   seeder, policy, controller, resource

php artisan make:migration add_slug_to_posts_table   # creates database/migrations/…
php artisan make:seeder PostSeeder       # database/seeders/PostSeeder.php
php artisan make:factory PostFactory --model=Post
```

#### HTTP layer

```bash
php artisan make:controller PostController --resource  # index/create/store/show/edit/update/destroy
php artisan make:controller PostController --api       # resource minus create & edit (for APIs)
php artisan make:controller PostController --invokable # single __invoke() method
php artisan make:request StorePostRequest  # app/Http/Requests/ — validation + authorization
php artisan make:resource PostResource     # JSON API resource transformer
php artisan make:middleware CheckRole      # app/Http/Middleware/
php artisan make:policy PostPolicy --model=Post   # app/Policies/
```

#### Async & notifications

```bash
php artisan make:job ProcessOrder          # app/Jobs/ — runs on a queue
php artisan make:event OrderPlaced         # app/Events/
php artisan make:listener SendConfirmation --event=OrderPlaced
php artisan make:observer PostObserver --model=Post   # model lifecycle hooks
php artisan make:notification OrderShipped  # app/Notifications/ (mail, SMS, Slack, …)
php artisan make:mail WelcomeMail           # app/Mail/
php artisan make:command SendReminders      # custom artisan command
```
