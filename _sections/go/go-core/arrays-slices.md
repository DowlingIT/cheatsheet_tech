---
title: Arrays & Slices
subtopic: go-core
group: Collections
order: 1
---

#### Arrays vs slices

```go
var a [3]int              // fixed-size array
s := []int{1, 2, 3}         // slice — dynamic, backed by an array
s = append(s, 4)              // may reallocate
s2 := s[1:3]                    // sub-slice — shares the underlying array
len(s)   cap(s)
```

#### Common operations

```go
s := make([]int, 0, 10)         // len 0, cap 10
copy(dst, src)
s = append(s[:i], s[i+1:]...)     // remove the element at index i
```
