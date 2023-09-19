## Pointer Receivers, Referencing, Dereferencing
 
>Date: 2023-08-30  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #golang #programming  

### No need to Dereference
- Point is referenced as `p`, not `*p`
- Dereferencing is automatic with `.` operator
```go
func (p *Point) OffsetX(v int) {
	p.x = p.x + v
}
```
### No need to reference
- Do not need to reference when calling the method
```go
func main() {
	p := Point{3, 4}
	p.OffsetX(5)
	fmt.Println(p.x)
}
```
### Good practices
- All methods for a type have pointer receivers, or
- All methods for a type have non-pointer receiver
- Mixing pointer/non-pointer receivers for a type will get confusing (Pointer receiver allows modification)

---
- [Home](https://heartthymes.github.io)