---
title: fmt & Formatting
subtopic: go-core
group: Strings & Formatting
order: 2
---

#### Printf verbs

```go
fmt.Printf("%d %s %f\n", 42, "hi", 3.14)
fmt.Printf("%v\n", val)      // default format, any type
fmt.Printf("%+v\n", val)       // struct fields with names
fmt.Printf("%T\n", val)          // type of val
fmt.Sprintf("%5d", 42)             // '   42' — width padding
fmt.Sprintf("%.2f", 3.14159)         // '3.14'
```
