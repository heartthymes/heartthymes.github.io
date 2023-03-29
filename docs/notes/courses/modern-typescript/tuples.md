## Tuples
 
>Date: 2023-03-22  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #typescript #programming 

Tuple is a hybrid data structure combining qualities of array and object at the same time. 
```ts
// initialize a tuple
const myTuple: [boolean, number, string] = [true, 10, "ten"]

// indexed referensing and pushing
myTuple[0] = false // [false, 10, 'ten']
```

Tuples exist only in TS, they are represented as arrays in JS. However there is an initiative to add tuples to JS.

```ts
// By using a spread operator we can let unlimited number of values
// Both of this examples are valid
const myTuple: [boolean, number, ...string[]] = [true, 10, "ten", "nine", "my string"]

const myTuple2: [...boolean[], number, string] = [true, false, true, 10, "ten"]

```

---
- [Home](https://heartthymes.github.io)