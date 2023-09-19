## Interface vs Concrete Types
 
>Date: 2023-08-30  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #golang #programming  

### Interface values
- Can be treated like other values
	- Assigned to variables
	- Passed, returned
- Interface values have two components
	- Dynamic Type: Concrete type which it is assigned to
	- Dynamic Value: Value of the dynamic type
- Interface value is actually a pair
```go
type Speaker interface { // Interface
	Speak()
}

type Dog struct { // Dynamic type
	name string
}

func (d Dog) Speak() { // Implemetation of the interface
	fmt.Println(d.name)
}

func main() {
	var s1 Speaker
	var d1 Dog { "Brian" } // Dynamic value
	s1 = d1
	s1.Speak()
}
```
- An interface can have nil dynamic value
```go
var s1 Speaker
var d1 *Dog
s1 = d1
// d1 has no concrete type yet
// s1 has a dynamic type but no dynamic value
```
### Nil dynamic value
- Can still call the Speak() method of s1
- Doesn't need a dynamic value to call
- Need to check inside the method
```go
func (d *Dog) Speak() {
	if d == nil {
		fmt.Println("<noise>")
	} else {
		fmt.Println(d.name)
	}
}

var s1 Speaker
var d1 *Dog
s1 = d1
s1.Speak
```
### Nil interface value
- Interface with nil dynamic type
- Very different from an interface with nil dynamic value
- Nil dynamic value and valid dynamic type
	- Can call a method since type is known
```go
var s1 Speaker
var d1 *Dog
s1 = d1
```
- Nil dynamic type
	- Cannot call a method, runtime error
```go
var s1 Speaker
```

---
- [Home](https://heartthymes.github.io)