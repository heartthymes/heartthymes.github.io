## Slices
A slice is a dynamically-sized, flexible view into the elements of an array.
```go
a := make([]int, 3) // Int slice of length 3, zero-valued [0, 0, 0]
b := make([]int, 3, 5) // Int slice of length 3 and capacity 5
a[0] = 1 // Setting and getting are the same as for an array [1, 0, 0]
a = append(a, 1, 2) // [1, 0, 0, 1, 2]
```
Slices are half-open, first element is included, last - excluded.
```go
primes := [6]int{2, 3, 5, 7, 11, 13}
var s []int = primes[1:4] // Elements from 1 to 3
```
Slices are views on an underlying array. It doesn't contain any data. Modifying values will modify them in the underlying array.
```go
// This will create an array
[3]bool{true, false, true}
//This will create the same array and then build a slice that references it
[]bool{true, false, true}
```
Slices can contain structs
```go
s := []struct {
		i int
		b bool
	}{
		{2, true},
		{3, false},
		{5, true},
		{7, true},
		{11, false},
		{13, true},
	}
```
Slices a populated with default values if nothing provided. These expressions are equivalent:
```go
a[0:10]
a[:10]
a[0:]
a[:]
```
Slices contain both length and capacity. Length - is the number of elements it contains. And capacity - is the number of elements in the underlying array.
```go
	s := [3]int{1, 2, 3}
	a := s[0:1]
	len(a) // Slice length
	cap(a) // Slice capacity
```
There are also nil slices
```go
var s []int // Nil slice
```

## String Packets
 
>Date: 2023-03-29  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #golang #programming  

There is a package called `utf`. It provides variety of methods to work with runes. For example:
*Boolean checks*
- `IsDigit(r rune)`
- `IsSpace(r rune)`
- `IsLetter(r rune)`
- `IsLower(r rune)`
- `IsPunct(r rune)`
*Conversions*
- `ToUpper(r rune)`
- `ToLower(r rune)`

`strings` package examples:
- `Compare(a, b)`
- `Contans(s, substr)`
- `HasPrefix(s, prefix)`
- `Index(s, substr)`
- `Replace(s, old, new, n)`
- `ToLower(s)`
- `ToUpper(s)`
- `TrimSpace(s)`
- `Atoi(s)`
- `Itoa(s)`
- `FormatFloat(f, fmt, prec, bitSize)`
- `ParseFloat(s, bitSize)`

---
- [Home](https://heartthymes.github.io)