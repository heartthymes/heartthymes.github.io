## Type: Never
 
>Date: 2023-03-22  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #typescript #programming 

If a function returns `void` it still returns `undefined`
In case of the exception is thrown or code never finishes, function returns nothing. Type `never` serves as a description in such cases.
```ts
//This function never returns
const myError = (msg: string) => {
	throw new Error(msg);
}

//This function never stops
const neverEnds = () => {
 while() {
	 //some code
 }
}
```
Type never can't be assigned

---
- [Home](https://heartthymes.github.io)