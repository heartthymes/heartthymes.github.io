## Using Interfaces
 
>Date: 2023-08-30  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #golang #programming  

- Need a function which takes multiple types as a parameter
- Function foo() parameter can be of Type X or Type Y
- Define interface Z
- foo() parameter is interface Z
- Types X and Y satisfy Z
- Interface methods must be those needed by foo()
```go
type Shape2D interface {
	Area() float64
	Perimeter() float64
}

type Triangle {...}
func (t Triangle) Area float64 {...}
func (t Triangle) Perimeter float64 {...}
type Rectangle {...}
func (t Rectangle) Area float64 {...}
func (t Rectangle) Perimeter float64{...}

func FitInYard(s Shape2D) bool {
	if (s.Area() < 100 &&
		s.Perimeter() < 100) {
			return true
	}
	return false
}
```
### Empty interface
```go
func PrintMe(val interface{}) {
	fmt.Println(val)
}
```
- Empty interface specifies no methods
- All types satisfy empty interface
- Use it to have a function accept any type as parameter

---
- [Home](https://heartthymes.github.io)