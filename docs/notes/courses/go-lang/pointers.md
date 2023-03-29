## Pointers
 
>Date: 2023-03-29  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #golang #programming  

A pointer is an address to some data in memory.
- `&` - returns the address of a variable/function  
- `*` - returns data at an address (dereferencing)  
Method `new()` creates variable. initializes it with zero value and returns a pointer to it.
```go
ptr := new(int) // now ptr contains an address of int
*ptr = 3 // setting value for ptr reference to 3 using *
```

---
- [Home](https://heartthymes.github.io)