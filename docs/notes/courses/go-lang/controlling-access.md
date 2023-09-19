## Controlling Access
 
>Date: 2023-08-30  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #golang #programming  

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

---
- [Home](https://heartthymes.github.io)