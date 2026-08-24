---
title: Declarations
subtopic: go-core
group: Variables & Types
order: 1
---

#### var, :=, const

```go
var name string = "Alice"
var age int                 // zero value: 0
x := 42                       // short declaration — type inferred, function scope only

const Pi = 3.14159
const (
    A = iota   // 0
    B          // 1
    C          // 2
)
```
