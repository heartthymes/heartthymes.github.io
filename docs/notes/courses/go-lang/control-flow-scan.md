## Control flow, scan
 
>Date: 2023-03-29  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #golang #programming  

### Control flow
```go
switch {
	case x > 1:
		//some code
	case x < 0
		//some code
}

i := 0
for i < 10 {
	i++
	if i == 6 { break } // stops the loop
}

for i < 10 {
	i++
	if i == 6 { continue } // stops the current iteration
	// some code
}
```

### Scan
Basic `Scan` method. Only usable for primitive cases. Has a lot of downsides.
```go
var num int

fmt.Printf("My num:")
num, err = fmt.Scan(&num) // basic scanner
fmt.Printf(num)
```

---
- [Home](https://heartthymes.github.io)