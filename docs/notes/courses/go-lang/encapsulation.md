## Encapsulation
 
>Date: 2023-08-30  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #golang #programming  

### Controlling Access
```go
package data
var x int = 1
func PrintX() {fmt.Println(x)}

package main
import "data"
func main() {
	data.PrintX()
}
```
### Controlling Access to Structs
```go
package data
type Point struct {
	x float64
	y float64
}
func (p *Point) InitMe(xn, yn float64) { // InitMe is needed to set private fields
	p.x = xn
	p.y = yn
}

func (p *Point) Scale(v float64) {
	p.x = p.x * v
	p.y = p.y * v
}

func (p *Point) PrintMe() {
	fmt.Println(p.x, p.y)
}

package main
func main() {
	var p data.Point
	p.InitMe(3,4)
	p.Scale(2)
	p.PrintMe()
}
```

---
- [Home](https://heartthymes.github.io)