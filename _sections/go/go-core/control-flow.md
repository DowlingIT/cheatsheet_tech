---
title: Control Flow
subtopic: go-core
group: Operators & Control Flow
order: 2
---

#### if / switch / for

```go
if x > 0 {
} else if x < 0 {
} else {
}

switch day {
case "Mon", "Tue":
default:
}
```

#### Go has only `for`

```go
for i := 0; i < 10; i++ { }   // classic
for cond { }                    // while-style
for { }                           // infinite
for i, v := range items { }         // range over slice/map/string/channel
```
