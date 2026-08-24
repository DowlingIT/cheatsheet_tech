---
title: Structs & Methods
subtopic: go-core
group: Structs & Interfaces
order: 1
---

#### Struct & method

```go
type Point struct {
    X, Y int
}

func (p Point) String() string {           // value receiver — gets a copy
    return fmt.Sprintf("(%d, %d)", p.X, p.Y)
}

func (p *Point) Scale(f int) {             // pointer receiver — can mutate
    p.X *= f
    p.Y *= f
}
```

#### Embedding

```go
type Base struct { ID int }
type User struct {
    Base       // embedded — promotes Base's fields & methods
    Name string
}
u := User{Base: Base{ID: 1}, Name: "Alice"}
u.ID   // promoted field access
```
