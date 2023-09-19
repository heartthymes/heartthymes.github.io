## Passing Arrays and Slices
 
>Date: 2023-08-30  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #golang #programming  

- Array arguments are copied
- Arrays can be big, so this is a problem
```go
func foo(x [3]int) int {
	return x[0]
}

func main() {
	a := [3]int{1,2,3}
	fmt.Print(foo(a))
}
```
- It is possible to pass array pointers
```go
func foo(x *[3]int) {
	(*x)[0] = (*x)[0] + 1
}

func main() {
	a := [3]int{1,2,3}
	foo(&a)
	fmt.Print(a)
}
```
- Messy and unnecessary
- It's better to pass Slices instead
- Passing a slice copies the pointer
```go
func foo(sli []int) {
	sli[0] = sli[0] + 1
}

func main() {
	a := []int{1,2,3}
	foo(a)
	fmt.Print(a)
}
```

---
- [Home](https://heartthymes.github.io)