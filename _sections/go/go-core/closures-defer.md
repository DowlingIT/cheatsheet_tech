---
title: Closures & Defer
subtopic: go-core
group: Functions
order: 2
---

#### defer & panic/recover

```go
func readFile(path string) error {
    f, err := os.Open(path)
    if err != nil { return err }
    defer f.Close()   // runs when readFile returns, in LIFO order
    // ...
    return nil
}

func safeDivide() (result int) {
    defer func() {
        if r := recover(); r != nil { result = -1 }
    }()
    panic("boom")
}
```

#### Closures

```go
func counter() func() int {
    n := 0
    return func() int { n++; return n }   // closes over n
}
c := counter()
c()   // 1
c()   // 2
```
