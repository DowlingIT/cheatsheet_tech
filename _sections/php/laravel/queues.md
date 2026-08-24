---
title: Queues & Jobs
subtopic: laravel
group: Helpers & Events
order: 2
---

#### Dispatching

```php
ProcessOrder::dispatch($order);
ProcessOrder::dispatch($order)->delay(now()->addMinutes(5));
ProcessOrder::dispatchIf($order->isPaid(), $order);

// Helper
dispatch(new SendEmail($user));
dispatch(fn() => $order->process());     // closure job
```

#### Job class

```php
class ProcessOrder implements ShouldQueue {
    use Dispatchable, InteractsWithQueue, Queueable, SerializesModels;

    public int $tries = 3;
    public int $timeout = 60;

    public function __construct(public Order $order) {}

    public function handle(): void {
        // do work
    }

    public function failed(\Throwable $e): void {
        // notify on failure
    }
}
```

#### Run worker

```bash
php artisan queue:work
php artisan queue:work --queue=emails --tries=3
php artisan queue:failed      # list failed jobs
php artisan queue:retry all
```
