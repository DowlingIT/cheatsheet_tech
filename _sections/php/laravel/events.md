---
title: Events & Observers
subtopic: laravel
group: Helpers & Events
order: 3
---

#### Dispatching events

```php
// Dispatch
OrderPlaced::dispatch($order);
event(new OrderPlaced($order));        // helper equivalent

// Dispatch and wait for all listeners to finish
OrderPlaced::dispatchSync($order);
```

#### Listener class

```php
// app/Listeners/SendOrderConfirmation.php (auto-discovered)
class SendOrderConfirmation implements ShouldQueue {  // ShouldQueue → runs on queue
    public function handle(OrderPlaced $event): void {
        Mail::to($event->order->user)
            ->send(new OrderConfirmation($event->order));
    }
}
```

#### Observers (model lifecycle)

```php
class PostObserver {
    public function creating(Post $post): void { }  // before INSERT
    public function created(Post $post): void { }   // after INSERT
    public function updating(Post $post): void { }
    public function updated(Post $post): void { }
    public function deleting(Post $post): void { }
    public function deleted(Post $post): void { }
    public function restored(Post $post): void { }  // after SoftDelete restore
}

// Register in AppServiceProvider::boot()
Post::observe(PostObserver::class);
```
