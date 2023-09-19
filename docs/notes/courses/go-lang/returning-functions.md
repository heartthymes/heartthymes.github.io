## Returning Functions
 
>Date: 2023-08-30  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #golang #programming  

### Function Defines a Funcition
```go
func MakeDistOrigin(o_x, o_y float64) func (float64, float64) float64 {
	fn := func (x, y, float64) float64 {
		return math.Sqrt(math.Pow(x - o_x, 2) + math.Pow(y - o_y, 2))
	}
	return fn
}

func main() {
	Dist1 := MakeDistOrigin(0, 0)
	Dist2 := MakeDistOrigin(2, 2)
	// Dist1 and Dist2 have different origins
	fmt.Println(Dist1(2,2))
	fmt.Println(Dist2(2,2))
}
```
- Functions are passed/returned with their environment
- `o_x` and `o_y` are in the closure of `fn`

---
- [Home](https://heartthymes.github.io)