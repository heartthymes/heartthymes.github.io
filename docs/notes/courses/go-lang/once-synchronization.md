## Once synchronization
 
>Date: 2023-08-30  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #golang #programming  

- Initialization must happen once
- Initialization must happen before everything else
### Sync.Once
- Has one method `once.Do(f)`
- Function `f` is executed only one time
	- Even if it is called in multiple goroutines
- All calls to `once.Do()` block until the first returns
	- Ensures that initialization is executing first
```go
var wg sync.WaitGroup

func main() {
   wg.Add(2)
   go dostuff()
   go dostuff()
   wg.Wait()
}

var on sync.Once
func setup() {
	fmt.Println("Init")
}
func dostuff() {
	on.Do(setup) // setup() should execute only once
	fmt.Println("hello") // "hello" should not be printed until setup() returns
	wg.Done()
}

// Init
// hello
// hello
```

---
- [Home](https://heartthymes.github.io)