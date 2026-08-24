---
title: sync Package
subtopic: go-core
group: Concurrency
order: 2
---

#### WaitGroup & Mutex

```go
var wg sync.WaitGroup
for i := 0; i < 5; i++ {
    wg.Add(1)
    go func() { defer wg.Done(); doWork() }()
}
wg.Wait()

var mu sync.Mutex
mu.Lock()
counter++
mu.Unlock()
```
