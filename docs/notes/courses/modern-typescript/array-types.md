## Array types
 
>Date: 2023-03-22  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #typescript #programming 

Arrays in TS are the same as they are in JS, except it is possible to provide type to it
```ts
const myAnies: any[] = ["string", 1, true]
const myNums: number[] = [1, 2, 3]
const myTwoDims: number[][] = [[1, 2,3], [1,2,3]]
const myArrElement = myNums[0] // 1
```

To push element:
```ts
const arr: number[] = []
arr.push(1)
```

Array functions can be applied the usual way:
```ts
const arr: number[] = [1, 2, 3]
const b = arr.filter((n) => n != 0)
	.map((n) => n + 1)

// To maintain clearens of data types, inner parameters could be also typed explicitly

const b = arr.filter((n: number) => n != 0)
	.map((n: number) => n + 1)
```

Array destruction
```ts
const arr: number[] = [1, 2, 3]
const [first, second] = arr; //destructs the array and assign values to provided variables (constants in this case)
```

---
- [Home](https://heartthymes.github.io)