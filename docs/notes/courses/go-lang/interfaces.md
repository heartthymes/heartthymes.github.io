## Interfaces
 
>Date: 2023-08-30  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #golang #programming  

- Set of method signatures
	- Name, parameters, return values
	- Implementation is NOT defined
- Used to express conceptual similarity between types
- Type satisfies an interface if type defines all methods specified in the interface
	- Same method signatures
- Similar to inheritance with overriding
### Defining an interface
```go
type Shape2D interface {
	Area() float64
	Perimeter() float64
}

// Triangle type satisfies Shape2D interface by implementing all of the methods, no need to state it separately
type Triangle {...}
func (t Triangle) Area() float64 {...}
func (t Triangle) Perimeter() float64 {...}
```

---
- [Home](https://heartthymes.github.io)