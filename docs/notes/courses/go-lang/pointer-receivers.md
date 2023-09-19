## Pointer Receivers
 
>Date: 2023-08-30  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #golang #programming  

- Receiver is passed implicitly as an argument to the method
- Method cannot modify the data inside the receiver
```go
func main() {
	p1 := Point(3,4)
	p1.OffsetX(5) // OffsetX() should increase x coordinate
}
```
- If receiver is large, lots of copying is required
```go
type Image [100][100]int
func main() {
	i1 := GrabImage()
	i1.BlurImage() // 10000 ints copied to BlurImage()
}
```
- Receiver can be a pointer to a type
- Call by reference, pointer is passed to the method
```go
func (p *Point) OffsetX(v float64) {
	p.x = p.x + v
}
```

---
- [Home](https://heartthymes.github.io)