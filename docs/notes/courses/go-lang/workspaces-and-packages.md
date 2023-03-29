## Workspaces and Packages
 
>Date: 2023-03-29  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #golang #programming  

Go community tend to maintain the same structure to the code.
- One workspace for all projects.
- Workspace is defined by `GOPATH` variable.
- `src` folder for sources
- `bin` folder for executables
- `pkg` folder for packages (libraries)
It's a recommendation not a rule, however it he

`GOPATH` is defined during installations. Go Tool will assume that the code is inside `GOPATH` folder.

`Package` is a group of related sources files. Go allows import packages. This is how packages are connected to each other.

Every go program should have package `main` and needs to have a `main()` function

```go
package main

func main() {
}
```

---
- [Home](https://heartthymes.github.io)