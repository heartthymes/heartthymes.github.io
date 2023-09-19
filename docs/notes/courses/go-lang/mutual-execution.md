## Mutual execution
 
>Date: 2023-08-30  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #golang #programming  

### Variable sharing
- It is possible to concurrently share variable
- It is bad. *NOT Concurrency-Safe*
- Functions can be invoked concurrently without interfering with other goroutines
```go
var i int = 0
var wg sync.WaitGroup
func inc() {
   i = i + 1
   wg.Done()}
func main() {
wg.Add(2)
   go inc()
   go inc()
   wg.Wait()
   fmt.Println(i)
}
```

---
- [Home](https://heartthymes.github.io)