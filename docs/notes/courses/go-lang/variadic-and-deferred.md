## Variadic and Deferred
 
>Date: 2023-08-30  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #golang #programming  

### Variable Argument Number
- Functions can take a variable number of arguments
- `...` is used to specify
- Treated as slice inside
```go
func getMax(vals ...int) int {
	maxV := -1
	for _, v := range vals {
		if v > maxV {
			maxV = v
		}
	}
	return maxV
}

func main() {
	fmt.Println(getMax(1,3,6,4))
	vslice := []int{1,3,6,4}
	fmt.Println(getMax(vslice...))
}

```
### Deferred Function Calls
- Call can be deferred until the surrounding function completes
- Typically used for cleanup activities
```go
func main() {
	defer fmt.Println("Bye!")
	fmt.Println("Hello!")
}
```
- Arguments of a deferred call are evaluated immediately
```go
func main() {
	i := 1
	defer fmt.Println(i+1)
	i++
	fmt.Println("Hello!")
}
```

---
- [Home](https://heartthymes.github.io)