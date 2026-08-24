---
title: Idioms & Gotchas
subtopic: go-core
group: Terminology & Style
order: 2
---

#### Error handling idiom

```go
result, err := doWork()
if err != nil {
    return fmt.Errorf("doing work: %w", err)   // %w wraps the original error
}
```

#### Common gotchas

```go
var s []int          // nil slice — len(s) == 0, but s == nil is true
s2 := []int{}          // empty slice — len(s2) == 0, but s2 == nil is false

var i interface{} = (*MyError)(nil)
i != nil   // true! — a nil pointer wrapped in an interface is not a nil interface
```
