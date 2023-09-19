## Maps
 
>Date: 2023-08-30  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #golang #programming  

Maps are key/value data type
```go
m := make(map[string]int) // Create a nil map of string keys and int value
m1 := make(map[int]int){1:1, 2:1, 4:2} // Create and initialize map 
m["key1"] = 1 // Set the value for the key
v1 := m["key1"] // Get the value for the key

delete(m, "key1") // Removes key/value pair from the map

_, prs := m["key1"] // Second return on getting an element indicates if the key was present in the map
```

---
- [Home](https://heartthymes.github.io)