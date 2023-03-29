## Variable scope
 
>Date: 2023-03-29  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #golang #programming  

Variable scope works the same as in any other language
```go
// visible for both functions
var x = 4

func f() {
	var x = 5 // visible only inside the f() function
	fmt.Printf("%d", x)
}

func g() {
	fmt.Printf("%d", x)
}

```
Scopes are defined using `{}` known as block
- `{}` - explicit block
- Universe block - all Go source
- Package block  - all source in a package
- File block - all inside file
- Some statements where usage of curly braces is not required, such as `if`. `for`, `switch`. Each case in `switch` or `select` gets individual block.

---
- [Home](https://heartthymes.github.io)