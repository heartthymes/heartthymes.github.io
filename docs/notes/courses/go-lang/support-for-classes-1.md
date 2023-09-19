## Support for Classes (1)
 
>Date: 2023-08-30  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #golang #programming  

## Support for Classes (1)
- There is no `class` keyword
- Methods are associated with data
```go
type MyInt int

func (mi MyInt) Double () int {
	return int(mi*2)
}

func main() {
	v := MyInt(3)
	fmt.Println(v.Double())
}
```
- Object v is an implicit argument to the method
- Call by value

---
- [Home](https://heartthymes.github.io)