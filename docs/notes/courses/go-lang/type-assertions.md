## Type Assertions
 
>Date: 2023-08-30  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #golang #programming  

- Type can be asserted from the interface if needed
```go
func DrawShape(s Shape2D) bool {
	rect, ok := s.(Rectangle)
	if ok {
		DrawRect(rect)
	}
	tri, ok := s.(Triangle)
	if ok {
		DrawTriangle(tri)
	}
}
```
- Switch statement based on type
```go
func DrawShape(s Shape2D) bool {
	switch sh := s.(type) {
		case Rectangle:
			DrawRect(sh)
		case Triangle:
			DrawTriangle(sh)
	}
}
```

---
- [Home](https://heartthymes.github.io)