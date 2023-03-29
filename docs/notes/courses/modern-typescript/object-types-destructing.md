## Object types destructing

>Date: 2023-03-22  
>Category: [00ComputerScience](links/00ComputerScience.md)  
>Tags: #typescript #programming 

Object is a structure containing data.
Here is an example of an object initialization, providing it as an argument to a typed function including destruction:
```ts
const myObj = {
	myBool: true,
	myNum: 10,
	myStr: "Thymes",
    myNestObj: {
        error: "Error"
    }
}

function myFunc({
        myBool,
        myNum,
        myStr,
        myNestObj:{error},
    }: {
		myBool: boolean;
		myNum: number;
		myStr: string;
        myNestObj: {
            error: string
        };
	}
) {
	console.log(myBool)
    console.log(myNum)
    console.log(myStr)
    console.log(error)
}

myFunc(myObj)

```

---
- [Home](https://heartthymes.github.io)