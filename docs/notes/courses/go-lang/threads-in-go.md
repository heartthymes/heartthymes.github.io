## Threads in GO
 
>Date: 2023-08-30  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #golang #programming  

### Goroutines
- One goroutine is created automatically to execute the main()
- Other goroutines are created using word `go`
```go
// Main goroutine blocks on foo() call
a = 1
foo()
a = 2

// New goroutine created for foo(). Main goroutine does not block
a = 1
go foo()
a = 2
```
- A goroutine exits when its code is complete
- When the main goroutine is complete, all other goroutines exit
- A goroutine may not complete its execution because main completes early
### Exiting Goroutines
```go
func main() {
	go fmt.Printf("New routine")
	fmt.Printf("Main routine")
}
```
- Only "Main routine" is printed
- Main finished before the new goroutine started
```go
func main() {
	go fmt.Printf("New routine")
	time.Sleep(100 * time.Millisecond)
	fmt.Printf("Main routine")
}
```
- Add a delay in the main routine to give the new routine a chance to complete
- "New routineMain routine" is now printed
- Add timing is bad, because may be wrong
- Need formal synchronization constructs
### Synchronization
- Using *global event* viewed by all threads simultaneously
```
// Task 1
x = 1
x = x + 1
// -> GLOBAL EVENT

// Task 2
if GLOBAL EVENT
	print x
```
### Sync WaitGroup
- Sync package contains functions to synchronize between goroutines
- sync.WaitGroup forces a goroutine to wait for other goroutines
- contains an internal counter
	- increment counter for each goroutine to wait for
	- Decrement counter when each goroutine completes
	- Waiting goroutine cannot continue until counter is 0
```go
func foo(wg *sync.WaitGroup) {
   fmt.Printf("New routine")
   wg.Done() // Decrementing counter
}
func main() {
   var wg sync.WaitGroup // Instantiating a new Wait Group
   wg.Add(1) // Incrementing the counter
   go foo(&wg) // Starting new goroutine, link to wait group is provided
   wg.Wait() // Start waiting based on counter
   fmt.Printf("Main routine")
}
```
### Communication
- Channels are used to transfer data between goroutines
- Channels are typed
- Use `make()` to create channel
```go
c := make(chan int)
```
- Send and receive data using the `<-` operator
```go
// Send data
c <- 3

// Receive data
x := <- c
```
Channel example
```go
func prod(v1 int, v2 int, c chan int) {
	c <- v1 * v2}
func main() {
	c := make(chan int)
	go prod(1, 2, c)
	go prod(3, 4, c)
	a := <- c
	b := <- c
	fmt.Println(a*b)
}
```
### Unbuffered channels
- Unbuffered channels cannot hold data in transit
	- Deafult is unbuffered
- Sending blocks until data is received
- Receiving blocks until data is sent
```go
// Task 1
c <- 3
// One houe later
//Task 2
x := <- c
```
- Channel communication is synchronous
- Blocking is the same as waiting for communications
- Receiving and ignoring the result is same as a Wait()
```go
// Task 1
c <- 3

// Task 2
<- c
```
### Buffered channels
- Channels can contain a limited number of objects
	- Default size is 0 (unbuffered)
- *Capacity* is the number of objects it can hold in transit
- Optional argument to `make()` defines channel capacity
```go
c := make(chan int, 3)
```
- Sending object blocks if buffer is full
- Receiving only blocks if buffer is empty
```go
// Task 1
c <- 3

// Task 2
a := <- c // This one blocks until send occurs
b := <- c // This one blocks forever
```
```go
// Task 1
c <- 3 
c <- 4 // Blocks until receive is done

// Task 2
a := <- c // Blocks until first send is done
```
- Sender and receiver do not need to operate at exactly the same speed
- Speed mismatch is acceptable
- Average speeds must still match

---
- [Home](https://heartthymes.github.io)