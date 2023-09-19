## Mutex
 
>Date: 2023-08-30  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #golang #programming  

- Don't let 2 goroutines write to a shared variable at the same time
- Need to restrict possible interleavings
- Access to shared variables cannot be interleaved
- Mutual execution. Code segments in different goroutines which cannot execute concurrently
- Writing to shared variables should be mutually exclusive
### Sync.Mutex
- Mutex ensures mutual exclusion
- Uses a binary semaphore
- Flag up - shared variable is in use
- Flag down - shared variable is available
- `Lock()` - method puts the flag up
	- Shared variable in use
- If lock is already taken by a goroutine, `Lock()` blocks until the flag is put down
- `Unlock()` method puts the flag down
	- Done using shared variable
- When `Unlock()` is called, a blocked `Lock()` can proceed
```go
var i int = 0
var mut sync.Mutex
func inc() {
	mut.Lock()
	i = i + 1
	mut.Unlock()
}
```

---
- [Home](https://heartthymes.github.io)