## Error Handling
 
>Date: 2023-08-30  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #golang #programming  

- Many Go programs return error interface objects to indicate errors
```go
type error interface {
	Error() string
}
```
- Correct operation: error == nil
- Incorrect operation: Error() prints error message
### Handling Errors
- Check whether the error is nil
- If it is not nil, handle it
```go
f, err := os.Open("/myfolder/test.txt")
if err != nil {
	fmt.Println(err)
	return
}
```
- `fmt` package calls the Error() method to generate string to print

---
- [Home](https://heartthymes.github.io)