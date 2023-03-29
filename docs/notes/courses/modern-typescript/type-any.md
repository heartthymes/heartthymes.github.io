## Type: Any
 
>Date: 2023-03-22  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #typescript #programming 

Type `any` represents an unknown type. Similar to Kotlin `Any` and Java `Object`.

Type conversion for the type `any` can be done on assignment:
```ts
const a = '{"key1":"value1", "key2":2}';

const b = JSON.parse(a) // b is of type any

const myObj: {
	key1: string;
	key2: number;
} = JSON.parse() //b is of type object

//From the perspective of JS b and myObj are both objects
```

---
- [Home](https://heartthymes.github.io)