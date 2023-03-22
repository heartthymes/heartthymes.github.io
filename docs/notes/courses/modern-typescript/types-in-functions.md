## Types in functions
 
>Date: 2023-03-22  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #typescript #programming 

Functions are enclosed blocks of code that can be reused
```ts
const agr1: string
let arg2: number

//declare a function
funtion myFunction(a: string, b: number): void {
// some code returning void type
}

//calling a function
myFunction(arg1, arg2)

//arrow function is also a function
const myfunc = (a: string, b: number): void => {
//some code returning void type
}

myfunc(arg1, arg2)
```

By default any function in typescript returns undefined.

---
- [Home](https://heartthymes.github.io)