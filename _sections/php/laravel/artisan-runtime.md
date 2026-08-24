---
title: Runtime Commands
subtopic: laravel
group: Artisan CLI
order: 2
---

#### Dev server & REPL

```bash
php artisan serve                        # start dev server — http://localhost:8000
php artisan serve --port=8080
php artisan tinker                       # interactive REPL (PsySH shell)
# In tinker: User::find(1)   Post::factory()->make()   DB::table('posts')->get()
```

#### Database

```bash
php artisan migrate                      # run all pending migrations
php artisan migrate:status               # show which migrations have run
php artisan migrate:fresh                # drop all tables and re-run all migrations
php artisan migrate:fresh --seed         # + run seeders (use in development only)
php artisan migrate:rollback             # undo last batch of migrations
php artisan migrate:rollback --step=3    # undo last 3 batches
php artisan db:seed                      # run DatabaseSeeder
php artisan db:seed --class=PostSeeder  # run a specific seeder
```

#### Cache & optimisation

```bash
php artisan cache:clear                  # clear application cache
php artisan config:clear                 # remove cached config
php artisan config:cache                 # cache config for production (faster boot)
php artisan route:clear                  # remove cached routes
php artisan route:cache                  # cache routes for production
php artisan view:clear                   # remove compiled Blade views
php artisan optimize                     # cache config + routes + views (production)
php artisan optimize:clear               # clear all caches
php artisan route:list --name=post       # list routes, filter by name pattern
```

#### Queues

```bash
php artisan queue:work                   # process jobs (keeps running — use supervisor)
php artisan queue:work --queue=emails    # process a specific named queue
php artisan queue:work --tries=3         # max attempts before job is marked failed
php artisan queue:listen                 # like work but re-loads code on each job
php artisan queue:failed                 # list all failed jobs
php artisan queue:retry all              # push all failed jobs back onto the queue
php artisan queue:flush                  # permanently delete all failed jobs
```
