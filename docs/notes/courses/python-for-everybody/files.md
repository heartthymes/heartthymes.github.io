 ## Files
 
>Date: 2023-03-05  
>Category: [00ComputerScience](links/00ComputerScience.md)
>Tags: #python #programming


```python
fhand = open('mbox.txt')      #opens a file
for line in fhand:            #iterating through lines
	line = line.rstrip()      #removing \n symbol
	if not "test" in line:    #looks for "test" in each line
		continue
```

---
- [Home](https://heartthymes.github.io)