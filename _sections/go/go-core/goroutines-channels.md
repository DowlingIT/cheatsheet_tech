---
title: Goroutines & Channels
subtopic: go-core
group: Concurrency
order: 1
---

#### Goroutines & channels

```go
go doWork()                     // runs concurrently

ch := make(chan int)              // unbuffered — blocks until received
ch2 := make(chan int, 10)           // buffered — up to 10 without blocking
ch <- 42                              // send
v := <-ch                               // receive
close(ch)
for v := range ch { }                     // reads until the channel is closed
```

#### select

```go
select {
case v := <-ch1:
    fmt.Println(v)
case ch2 <- 42:
    fmt.Println("sent")
default:
    fmt.Println("no channel ready")
}
```
