## Support for Classes (2)
 
>Date: 2023-08-30  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #golang #programming  

- Struct types compose data fields
- Structs and methods together allow arbitrary data and functions to be composed
```go
type Point struct {
	x float64
	y float64
}

func (p Point) DistToOrig() {
	t := math.Pow(p.x, 2) + math.Pow(p.y, 2)
	return math.Sqrt(t)
}

func main() {
	p1 := Point(3,4)
	fmt.Println(p1.DistToOrig())
}
```
### Encapsulation in Go
- Making data fields or methods hidden from the programmer
- Might use a `private` keyword in another language
- Example: Point struct, Scale() method
- Scale() should multiply x and y coordinates by a constant
- Don't trust this to a programmer
	- Might scale one coordinate but not the other
	- Coordinates could become inconsitent
	- Need to hide x and y coordinates
### Hiding in a Package
- Go can only hide data/methods in a package
- Variables/functions are only exported if their names start with *Capital letter*
```go
package data
var X int = 1
var Y int = 2

package main
import "data"
func main() {
	fmt.Println(Y)
	fmt.Println(X)
}
```

---
- [Home](https://heartthymes.github.io)