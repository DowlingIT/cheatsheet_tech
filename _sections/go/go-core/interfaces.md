---
title: Interfaces
subtopic: go-core
group: Structs & Interfaces
order: 2
---

#### Implicit implementation

```go
type Stringer interface {
    String() string
}

func describe(s Stringer) { fmt.Println(s.String()) }
describe(Point{1, 2})   // Point implements Stringer implicitly — no "implements" keyword
```

#### Empty interface & type assertion

```go
var val interface{} = 42        // or `any` (alias since Go 1.18)
n, ok := val.(int)                // type assertion, ok is false if the wrong type

switch v := val.(type) {          // type switch
case int:    fmt.Println("int", v)
case string: fmt.Println("string", v)
}
```
