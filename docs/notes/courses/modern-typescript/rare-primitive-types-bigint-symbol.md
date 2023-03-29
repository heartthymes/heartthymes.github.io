## Rare primitive types: bigint, symbol
 
>Date: 2023-03-22  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #typescript #programming 

Type `symbol` masks variable under a tag
```ts
let id: simbol = Symbol("id")

const data = {
	[id]: 1,
}

console.log(data[id])
```

Type `bigint` serves to store integer values bigger than possible in `int`. This type was introduces in later versions of ES and might not be valid for current target setting.
```ts
let a:bigint = 2n
```

---
- [Home](https://heartthymes.github.io)