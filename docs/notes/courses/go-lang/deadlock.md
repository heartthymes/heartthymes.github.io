## Deadlock
 
>Date: 2023-08-30  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #golang #programming  

- Synchronization causes the execution of different goroutines to depend on each other
```go
// G1
ch <- 1
mut.Unlock()

// G2
x := <- ch
mut.Lock()
```
- G2 cannot continue until G1 does something
- Circular dependencies causes all involved goroutine to block
- Can be caused by waiting on channels
```go
// Deadlock example
func dostuff(c1 chan int, c2 chan int) {
   <- c1
   c2 <- 1
   wg.Done()
}

func main() {
   ch1 := make(chan int)
   ch2 := make(chan int)
   wg.Add(2)
   go dostuff(ch1, ch2)
   go dostuff(ch2, ch1)
   wg.Wait()
}
```
- Golang runtime automatically detects when all goroutines are deadlocked
- Cannot detect when a subset of goroutines are deadlocked

---
- [Home](https://heartthymes.github.io)