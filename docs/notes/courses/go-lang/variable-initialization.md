## Variable initialization
 
>Date: 2023-03-29  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #golang #programming  

Variables are initialized with "zero" value, for `int` it's `0`, for `string` it's `""` (empty string)
```go
var x int = 1
var y int
var ip = *int // ip is a pointer to int

ip = &x // ip now points to x
y = *ip // y is now 1
```

---
- [Home](https://heartthymes.github.io)