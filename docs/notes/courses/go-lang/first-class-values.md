## First Class Values
 
>Date: 2023-08-30  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #golang #programming  

- Functions can be treated like other function types
- Variables can be declared with a function type
- Can be created dynamically
- Can be passed as arguments and returned as values
- Can be stored in data structures
### Variables as Functions
```go
var funcVar func(int) int
func incFn(x int) int {
	return x + 1
}

func main() {
	funcVar = incFn
	fmt.Print(funcVar(1))
}
```
### Functions as Arguments
```go
func applyIt(afunct func (int) int, val int) int {
	retur afunct(val)
}

func incFn(x int) int {return x + 1}
func decFn(x int) int {return x - 1}

func main() {
	fmt.Println(applyIt(incFn, 2))
	fmt.Println(applyIt(decFn, 2))
}
```
### Anonymous Functions
```go
func applyIt(afunct func (int) int, val int) {
	return afunct(val)
}

func main() {
	v := applyIt(func (x int) int {
			return x + 1
		}, 2)
	fmt.Println(v)
}
```

---
- [Home](https://heartthymes.github.io)