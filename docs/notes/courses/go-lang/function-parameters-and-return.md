## Function Parameters and Return
 
>Date: 2023-08-30  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #golang #programming  

Functions in go are declared the same way they are everywhere:
```go
func foo() { // zero parameter func
}

func foo(x int, y int) { // two parameter func
	fmt.Print(x * y)
}

func foo(x, y int) { // shortened parameter declaration (they are of the same type)
}

func foo (x int) int { // return value type after parameter declaration
	return x + 1
}

func foo (x int) (int, int) { // multiple return value types
	return x, x + 1 // multiple return values
}

d, v := foo(2) // call for the function returning more than one value

y := foo(1) // call

func main() {
	foo(2, 3) //call
}
```

---
- [Home](https://heartthymes.github.io)