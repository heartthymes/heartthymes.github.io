## Call By Value, Reference
 
>Date: 2023-08-30  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #golang #programming  

If called by value:
 - Passed arguments are copied to parameters.
 - Parameters are encapsulated inside the function
```go
func foo(y int) {
	y = y + 1
}
func main() {
	x:=2
	foo(x)
	fmt.Print(x)
}
``` 
- Function variables are only changed inside the function
- Copying is taking a lot of time. Slow for large objects

If called by reference:
- Pointers can be passed as an arguments to a function
- Function has a direct access to the variable in memory
```go
func foo(y *int) {
	*y = *y + 1
}
func main() {
	x := 2
	foo(&x)
	fmt.Print(x)
}
```
- Doesn't need to copy values of the arguments
- Data is not encapsulated
- Function variables can be modified during execution (possible race condition?)

---
- [Home](https://heartthymes.github.io)