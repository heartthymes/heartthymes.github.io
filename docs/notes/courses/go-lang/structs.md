## Structs
 
>Date: 2023-08-30  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #golang #programming  

Struct is a mutable collection of fields.
```go
// Struct declaration
type Vertex struct {
	X int
	Y int
}
// Struct initialization
p := Vertex{1, 2}
// Struct field mutation
p.X = 4

v := Vertex{1, 2}
p := &v
p.X = 1e9 // Shortened version of (*p).X. Using pointer.

v1 = Vertex{1, 2}  // has type Vertex
v2 = Vertex{X: 1}  // Y:0 is implicit
v3 = Vertex{}      // X:0 and Y:0
p  = &Vertex{1, 2} // has type *Vertex
```

---
- [Home](https://heartthymes.github.io)