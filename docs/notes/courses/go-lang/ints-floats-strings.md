## Ints, Floats, Strings
 
>Date: 2023-03-29  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #golang #programming  

### Ints
Type conversion of Ints
```go
// type conversion
var x int32 = 1
var y int64 = 2

x = y // error
x = int32(y) // type conversion
```

### Floats
- float32 - ~6 digit precision
- float64 - ~15 digits precision
```go
var x float64 = 123,45
var y float64 = 1.2345e2
```

### Complex numbers
Complex numbers represented as two floats: real and imaginary
```go
var z complex128 = complex(2,3)
```

### Strings
UTF-8 is a default encoding in Go. One character called `rune`.
Strings are immutable
```go
x := "Hello there" // is a string, but also a sequence or runes
```

---
- [Home](https://heartthymes.github.io)