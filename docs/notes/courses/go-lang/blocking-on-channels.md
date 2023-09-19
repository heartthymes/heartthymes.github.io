## Blocking on channels
 
>Date: 2023-08-30  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #golang #programming  

### Iterating through a channel
- Common to iteratively read from a channel
```go
for i := range c {
	fmt.Println(i)
}
```
- Continues to read from channel `c`
- One iteration each time a new value is reveived
- i is assigned to the read value
- Iterates when sender calls `close(c)`
### Receiving from a Multiple Goroutines
- Multiple channels may be used to receive from multiple sources
- Data from both sources may be needed
- Read sequentially
```go
a := <- c1
b := <- c2
fmt.Println(a*b)
```
### Select statement
- May have a choice of which data to use
	- i.e. First-come first-serve
```go
select {
	case a = <- c1:
		fmt.Println(a)
	case b = <- c2:
		fmt.Println(b)
}
```
- May select either send or receive operations
```go
select {
	case a = <- inchan:
		fmt.Println("Received a")
	case outchan <- b:
		fmt.Println("Sent b")
}
```
- May want to receive data until an *abort signal* is received
```go
for {
	select {
		case a <- c:
			fmt.Println(a)
		case <- abort:
			return
	}
}
```
- May want a default operation to avoid blocking
```go
select {
	case a = <- c1:
		fmt.Println(a)
	case b = <- c2:
		fmt.Println(b)
	default:
		fmt.Println("nop")
}
```

---
- [Home](https://heartthymes.github.io)